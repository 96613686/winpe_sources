# DloadMakePermanentImageCommit

- ea: `0x140014dc0`
- end: `0x140014e77`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014e80`

## callees

- `0x140014dc0`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x140014dfd`
- `KERNEL32!VirtualQuery` at `0x140014dfd`
- `KERNEL32!GetSystemInfo` at `0x140014e19`
- `KERNEL32!GetSystemInfo` at `0x140014e19`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  memset(&v8, 0, sizeof(v8));
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  result = VirtualQuery((LPCVOID)a1, &v8, 0x30u);
  if ( !result )
    __fastfail(0x19u);
  if ( (v8.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v6 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v7 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((SystemInfo.dwPageSize - 1) & (unsigned int)a1)
                           + ((SystemInfo.dwPageSize - 1) & (unsigned int)a2))
        - 1)
       / SystemInfo.dwPageSize;
    for ( result = (unsigned int)v7; result; --result )
    {
      _InterlockedOr(v6, 0);
      v6 = (volatile signed __int32 *)((char *)v6 + dwPageSize);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014dc0  mov     rax, rsp
0x140014dc3  mov     [rax+8], rbx
0x140014dc7  push    rdi
0x140014dc8  sub     rsp, 80h
0x140014dcf  xorps   xmm0, xmm0
0x140014dd2  xorps   xmm1, xmm1
0x140014dd5  mov     rdi, rdx
0x140014dd8  mov     r8d, 30h ; '0'; dwLength
0x140014dde  lea     rdx, [rax-68h]; lpBuffer
0x140014de2  mov     rbx, rcx
0x140014de5  movups  xmmword ptr [rax-68h], xmm0
0x140014de9  movups  xmmword ptr [rax-58h], xmm0
0x140014ded  movups  xmmword ptr [rax-48h], xmm0
0x140014df1  movups  xmmword ptr [rax-38h], xmm1
0x140014df5  movups  xmmword ptr [rax-28h], xmm1
0x140014df9  movups  xmmword ptr [rax-18h], xmm1
0x140014dfd  call    cs:__imp_VirtualQuery
0x140014e03  test    rax, rax
0x140014e06  jnz     short loc_140014E0D
0x140014e08  lea     ecx, [rax+19h]
0x140014e0b  int     29h; Win8: RtlFailFast(ecx)
0x140014e0d  test    [rsp+88h+var_44], 44h
0x140014e12  jz      short loc_140014E66
0x140014e14  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x140014e19  call    cs:__imp_GetSystemInfo
0x140014e1f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x140014e24  xor     edx, edx
0x140014e26  mov     eax, edi
0x140014e28  mov     r8d, r9d
0x140014e2b  neg     r8
0x140014e2e  and     r8, rbx
0x140014e31  lea     ecx, [r9-1]
0x140014e35  and     eax, ecx
0x140014e37  and     ebx, ecx
0x140014e39  add     eax, ebx
0x140014e3b  dec     rax
0x140014e3e  add     rax, r9
0x140014e41  div     r9
0x140014e44  xor     edx, edx
0x140014e46  mov     rcx, rax
0x140014e49  mov     rax, rdi
0x140014e4c  div     r9
0x140014e4f  add     rcx, rax
0x140014e52  mov     eax, ecx
0x140014e54  test    ecx, ecx
0x140014e56  jz      short loc_140014E66
0x140014e58  lock or dword ptr [r8], 0
0x140014e5d  add     r8, r9
0x140014e60  sub     rax, 1
0x140014e64  jnz     short loc_140014E58
0x140014e66  mov     rbx, [rsp+88h+arg_0]
0x140014e6e  add     rsp, 80h
0x140014e75  pop     rdi
0x140014e76  retn
```
