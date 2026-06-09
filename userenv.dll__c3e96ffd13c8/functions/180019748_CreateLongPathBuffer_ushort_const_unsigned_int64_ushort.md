# _CreateLongPathBuffer(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180019748`
- end: `0x1800197f6`
- name: `?_CreateLongPathBuffer@@YAJPEBG_KPEAPEAG@Z`
- size: `174`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a200`

## callees

- `0x1800078a0`
- `0x1800080b4`
- `0x180009cb8`
- `0x180019748`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197de`

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
0x180019748  mov     rax, rsp
0x18001974b  mov     [rax+8], rbx
0x18001974f  mov     [rax+18h], rsi
0x180019753  mov     [rax+10h], rdx
0x180019757  push    rdi
0x180019758  sub     rsp, 20h
0x18001975c  mov     rsi, r8
0x18001975f  mov     qword ptr [rax+10h], 0
0x180019767  lea     r8, [rax+20h]; unsigned __int64 *
0x18001976b  mov     qword ptr [rax+20h], 0
0x180019773  lea     rdx, [rax+10h]; unsigned __int16 **
0x180019777  xor     edi, edi
0x180019779  call    ?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z; GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)
0x18001977e  mov     ebx, eax
0x180019780  test    eax, eax
0x180019782  js      short loc_1800197D1
0x180019784  mov     ebx, 8000h
0x180019789  cmp     [rsp+28h+arg_18], rbx
0x18001978e  jbe     short loc_180019797
0x180019790  mov     ebx, 80070057h
0x180019795  jmp     short loc_1800197D1
0x180019797  mov     edx, 10000h; uBytes
0x18001979c  mov     ecx, 40h ; '@'; uFlags
0x1800197a1  call    cs:__imp_LocalAlloc
0x1800197a7  mov     rdi, rax
0x1800197aa  test    rax, rax
0x1800197ad  jnz     short loc_1800197B6
0x1800197af  mov     ebx, 8007000Eh
0x1800197b4  jmp     short loc_1800197D1
0x1800197b6  mov     r8, [rsp+28h+arg_8]; unsigned __int16 *
0x1800197bb  mov     rdx, rbx; unsigned __int64
0x1800197be  mov     rcx, rdi; unsigned __int16 *
0x1800197c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800197c6  mov     ebx, eax
0x1800197c8  test    eax, eax
0x1800197ca  js      short loc_1800197D1
0x1800197cc  mov     [rsi], rdi
0x1800197cf  xor     edi, edi
0x1800197d1  mov     rcx, [rsp+28h+arg_8]
0x1800197d6  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800197db  mov     rcx, rdi; hMem
0x1800197de  call    cs:__imp_LocalFree
0x1800197e4  mov     rsi, [rsp+28h+arg_10]
0x1800197e9  mov     eax, ebx
0x1800197eb  mov     rbx, [rsp+28h+arg_0]
0x1800197f0  add     rsp, 20h
0x1800197f4  pop     rdi
0x1800197f5  retn
```
