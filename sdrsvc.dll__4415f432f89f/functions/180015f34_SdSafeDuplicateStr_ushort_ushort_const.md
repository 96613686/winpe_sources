# SdSafeDuplicateStr(ushort * *,ushort const *)

- ea: `0x180015f34`
- end: `0x180015fbc`
- name: `?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z`
- size: `136`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800106f4`
- `0x180018f6c`
- `0x1800190bc`
- `0x180019e58`

## callees

- `0x180015cc8`
- `0x180015f34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015fa9`

## pseudocode

```c
__int64 __fastcall SdSafeDuplicateStr(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi

  if ( a1 )
  {
    *a1 = 0;
    v4 = 0;
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      v8 = v7;
      if ( v7 )
      {
        v4 = StringCchCopyNW(v7, v6, a2, v6);
        if ( v4 < 0 )
          CoTaskMemFree(v8);
        else
          *a1 = v8;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015f34  push    rbx
0x180015f36  push    rbp
0x180015f37  push    rsi
0x180015f38  push    rdi
0x180015f39  push    r14
0x180015f3b  sub     rsp, 20h
0x180015f3f  xor     r14d, r14d
0x180015f42  mov     rbp, rdx
0x180015f45  mov     rdi, rcx
0x180015f48  test    rcx, rcx
0x180015f4b  jnz     short loc_180015F54
0x180015f4d  mov     ebx, 80070057h
0x180015f52  jmp     short loc_180015FAF
0x180015f54  mov     [rcx], r14
0x180015f57  mov     ebx, r14d
0x180015f5a  test    rbp, rbp
0x180015f5d  jz      short loc_180015FAF
0x180015f5f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015f63  inc     rax
0x180015f66  cmp     [rdx+rax*2], r14w
0x180015f6b  jnz     short loc_180015F63
0x180015f6d  inc     eax
0x180015f6f  mov     ebx, eax
0x180015f71  lea     rcx, [rax+rax]; cb
0x180015f75  call    cs:__imp_CoTaskMemAlloc
0x180015f7b  mov     rsi, rax
0x180015f7e  test    rax, rax
0x180015f81  jnz     short loc_180015F8A
0x180015f83  mov     ebx, 8007000Eh
0x180015f88  jmp     short loc_180015FAF
0x180015f8a  mov     r9, rbx; unsigned __int64
0x180015f8d  mov     r8, rbp; unsigned __int16 *
0x180015f90  mov     rdx, rbx; unsigned __int64
0x180015f93  mov     rcx, rsi; unsigned __int16 *
0x180015f96  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180015f9b  mov     ebx, eax
0x180015f9d  test    eax, eax
0x180015f9f  js      short loc_180015FA6
0x180015fa1  mov     [rdi], rsi
0x180015fa4  jmp     short loc_180015FAF
0x180015fa6  mov     rcx, rsi; pv
0x180015fa9  call    cs:__imp_CoTaskMemFree
0x180015faf  mov     eax, ebx
0x180015fb1  add     rsp, 20h
0x180015fb5  pop     r14
0x180015fb7  pop     rdi
0x180015fb8  pop     rsi
0x180015fb9  pop     rbp
0x180015fba  pop     rbx
0x180015fbb  retn
```
