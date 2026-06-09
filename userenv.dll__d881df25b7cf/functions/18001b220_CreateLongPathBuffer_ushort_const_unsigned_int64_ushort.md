# _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)

- ea: `0x18001b220`
- end: `0x18001b2db`
- name: `?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z`
- size: `187`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ab88`

## callees

- `0x18000778c`
- `0x180008940`
- `0x18000a638`
- `0x18001b220`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b279`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b279`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2bc`

## pseudocode

```c
__int64 __fastcall _CreateLongPathBuffer(const unsigned __int16 *a1, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rdi
  int LongProfilePathNameInternal; // ebx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v8; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  v4 = 0;
  LongProfilePathNameInternal = GetLongProfilePathNameInternal(a1, &v8, &v9);
  if ( LongProfilePathNameInternal >= 0 )
  {
    if ( v9 <= 0x8000 )
    {
      v6 = (unsigned __int16 *)LocalAlloc(0x40u, 0x10000u);
      v4 = v6;
      if ( v6 )
      {
        LongProfilePathNameInternal = StringCchCopyW(v6, 0x8000u, v8);
        if ( LongProfilePathNameInternal >= 0 )
        {
          *a3 = v4;
          v4 = 0;
        }
      }
      else
      {
        LongProfilePathNameInternal = -2147024882;
      }
    }
    else
    {
      LongProfilePathNameInternal = -2147024809;
    }
  }
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v8);
  LocalFree(v4);
  return (unsigned int)LongProfilePathNameInternal;
}

```

## disassembly

```asm
0x18001b220  mov     rax, rsp
0x18001b223  mov     [rax+8], rbx
0x18001b227  mov     [rax+18h], rsi
0x18001b22b  mov     [rax+10h], rdx
0x18001b22f  push    rdi
0x18001b230  sub     rsp, 20h
0x18001b234  mov     rsi, r8
0x18001b237  mov     qword ptr [rax+10h], 0
0x18001b23f  lea     r8, [rax+20h]; unsigned __int64 *
0x18001b243  mov     qword ptr [rax+20h], 0
0x18001b24b  lea     rdx, [rax+10h]; unsigned __int16 **
0x18001b24f  xor     edi, edi
0x18001b251  call    ?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z; GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)
0x18001b256  mov     ebx, eax
0x18001b258  test    eax, eax
0x18001b25a  js      short loc_18001B2AF
0x18001b25c  mov     ebx, 8000h
0x18001b261  cmp     [rsp+28h+arg_18], rbx
0x18001b266  jbe     short loc_18001B26F
0x18001b268  mov     ebx, 80070057h
0x18001b26d  jmp     short loc_18001B2AF
0x18001b26f  mov     edx, 10000h; uBytes
0x18001b274  mov     ecx, 40h ; '@'; uFlags
0x18001b279  call    cs:__imp_LocalAlloc
0x18001b280  nop     dword ptr [rax+rax+00h]
0x18001b285  mov     rdi, rax
0x18001b288  test    rax, rax
0x18001b28b  jnz     short loc_18001B294
0x18001b28d  mov     ebx, 8007000Eh
0x18001b292  jmp     short loc_18001B2AF
0x18001b294  mov     r8, [rsp+28h+arg_8]; unsigned __int16 *
0x18001b299  mov     rdx, rbx; unsigned __int64
0x18001b29c  mov     rcx, rdi; unsigned __int16 *
0x18001b29f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b2a4  mov     ebx, eax
0x18001b2a6  test    eax, eax
0x18001b2a8  js      short loc_18001B2AF
0x18001b2aa  mov     [rsi], rdi
0x18001b2ad  xor     edi, edi
0x18001b2af  mov     rcx, [rsp+28h+arg_8]
0x18001b2b4  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001b2b9  mov     rcx, rdi; hMem
0x18001b2bc  call    cs:__imp_LocalFree
0x18001b2c3  nop     dword ptr [rax+rax+00h]
0x18001b2c8  mov     rsi, [rsp+28h+arg_10]
0x18001b2cd  mov     eax, ebx
0x18001b2cf  mov     rbx, [rsp+28h+arg_0]
0x18001b2d4  add     rsp, 20h
0x18001b2d8  pop     rdi
0x18001b2d9  retn
```
