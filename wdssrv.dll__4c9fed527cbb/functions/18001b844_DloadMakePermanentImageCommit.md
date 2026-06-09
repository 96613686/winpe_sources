# DloadMakePermanentImageCommit

- ea: `0x18001b844`
- end: `0x18001b908`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b910`

## callees

- `0x18001b844`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18001b8a3`
- `KERNEL32!GetSystemInfo` at `0x18001b8a3`
- `KERNEL32!VirtualQuery` at `0x18001b881`
- `KERNEL32!VirtualQuery` at `0x18001b881`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

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
        + (unsigned __int64)(((unsigned int)a1 & (SystemInfo.dwPageSize - 1))
                           + ((unsigned int)a2 & (SystemInfo.dwPageSize - 1)))
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
0x18001b844  mov     rax, rsp
0x18001b847  mov     [rax+8], rbx
0x18001b84b  push    rdi
0x18001b84c  sub     rsp, 80h
0x18001b853  xorps   xmm0, xmm0
0x18001b856  xorps   xmm1, xmm1
0x18001b859  mov     rdi, rdx
0x18001b85c  mov     r8d, 30h ; '0'; dwLength
0x18001b862  lea     rdx, [rax-68h]; lpBuffer
0x18001b866  mov     rbx, rcx
0x18001b869  movups  xmmword ptr [rax-68h], xmm0
0x18001b86d  movups  xmmword ptr [rax-58h], xmm0
0x18001b871  movups  xmmword ptr [rax-48h], xmm0
0x18001b875  movups  xmmword ptr [rax-38h], xmm1
0x18001b879  movups  xmmword ptr [rax-28h], xmm1
0x18001b87d  movups  xmmword ptr [rax-18h], xmm1
0x18001b881  call    cs:__imp_VirtualQuery
0x18001b888  nop     dword ptr [rax+rax+00h]
0x18001b88d  test    rax, rax
0x18001b890  jnz     short loc_18001B897
0x18001b892  lea     ecx, [rax+19h]
0x18001b895  int     29h; Win8: RtlFailFast(ecx)
0x18001b897  test    [rsp+88h+var_44], 44h
0x18001b89c  jz      short loc_18001B8F6
0x18001b89e  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18001b8a3  call    cs:__imp_GetSystemInfo
0x18001b8aa  nop     dword ptr [rax+rax+00h]
0x18001b8af  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18001b8b4  xor     edx, edx
0x18001b8b6  mov     r8d, r9d
0x18001b8b9  neg     r8
0x18001b8bc  and     r8, rbx
0x18001b8bf  lea     ecx, [r9-1]
0x18001b8c3  mov     eax, ecx
0x18001b8c5  and     ecx, ebx
0x18001b8c7  and     eax, edi
0x18001b8c9  add     eax, ecx
0x18001b8cb  dec     rax
0x18001b8ce  add     rax, r9
0x18001b8d1  div     r9
0x18001b8d4  xor     edx, edx
0x18001b8d6  mov     rcx, rax
0x18001b8d9  mov     rax, rdi
0x18001b8dc  div     r9
0x18001b8df  add     rcx, rax
0x18001b8e2  mov     eax, ecx
0x18001b8e4  test    ecx, ecx
0x18001b8e6  jz      short loc_18001B8F6
0x18001b8e8  lock or dword ptr [r8], 0
0x18001b8ed  add     r8, r9
0x18001b8f0  sub     rax, 1
0x18001b8f4  jnz     short loc_18001B8E8
0x18001b8f6  mov     rbx, [rsp+88h+arg_0]
0x18001b8fe  add     rsp, 80h
0x18001b905  pop     rdi
0x18001b906  retn
```
