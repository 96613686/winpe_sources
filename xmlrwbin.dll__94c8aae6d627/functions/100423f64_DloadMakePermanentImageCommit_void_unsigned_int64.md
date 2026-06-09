# DloadMakePermanentImageCommit(void *,unsigned __int64)

- ea: `0x100423f64`
- end: `0x100423ffc`
- name: `?DloadMakePermanentImageCommit@@YAXPEAX_K@Z`
- size: `152`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1004240a4`

## callees

- `0x100423f64`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x100423f82`
- `KERNEL32!VirtualQuery` at `0x100423f82`
- `KERNEL32!GetSystemInfo` at `0x100423f9e`
- `KERNEL32!GetSystemInfo` at `0x100423f9e`

## pseudocode

```c
void __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  __int64 dwPageSize; // r9
  volatile signed __int32 *v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  if ( !VirtualQuery((LPCVOID)a1, &Buffer, 0x30u) )
    __fastfail(0x19u);
  if ( (Buffer.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v5 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v6 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((unsigned int)a1 & (SystemInfo.dwPageSize - 1))
                           + ((unsigned int)a2 & (SystemInfo.dwPageSize - 1)))
        - 1)
       / SystemInfo.dwPageSize;
    v7 = (unsigned int)v6;
    if ( (_DWORD)v6 )
    {
      do
      {
        _InterlockedOr(v5, 0);
        v5 = (volatile signed __int32 *)((char *)v5 + dwPageSize);
        --v7;
      }
      while ( v7 );
    }
  }
}

```

## disassembly

```asm
0x100423f64  mov     [rsp+arg_0], rbx
0x100423f69  push    rdi
0x100423f6a  sub     rsp, 80h
0x100423f71  mov     rdi, rdx
0x100423f74  mov     r8d, 30h ; '0'; dwLength
0x100423f7a  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x100423f7f  mov     rbx, rcx
0x100423f82  call    cs:__imp_VirtualQuery
0x100423f88  test    rax, rax
0x100423f8b  jnz     short loc_100423F92
0x100423f8d  lea     ecx, [rax+19h]
0x100423f90  int     29h; Win8: RtlFailFast(ecx)
0x100423f92  test    byte ptr [rsp+88h+Buffer.Protect], 44h
0x100423f97  jz      short loc_100423FEB
0x100423f99  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x100423f9e  call    cs:__imp_GetSystemInfo
0x100423fa4  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x100423fa9  xor     edx, edx
0x100423fab  mov     r8d, r9d
0x100423fae  neg     r8
0x100423fb1  and     r8, rbx
0x100423fb4  lea     ecx, [r9-1]
0x100423fb8  mov     eax, ecx
0x100423fba  and     ecx, ebx
0x100423fbc  and     eax, edi
0x100423fbe  add     eax, ecx
0x100423fc0  dec     rax
0x100423fc3  add     rax, r9
0x100423fc6  div     r9
0x100423fc9  xor     edx, edx
0x100423fcb  mov     rcx, rax
0x100423fce  mov     rax, rdi
0x100423fd1  div     r9
0x100423fd4  add     rcx, rax
0x100423fd7  mov     eax, ecx
0x100423fd9  test    ecx, ecx
0x100423fdb  jz      short loc_100423FEB
0x100423fdd  lock or dword ptr [r8], 0
0x100423fe2  add     r8, r9
0x100423fe5  sub     rax, 1
0x100423fe9  jnz     short loc_100423FDD
0x100423feb  mov     rbx, [rsp+88h+arg_0]
0x100423ff3  add     rsp, 80h
0x100423ffa  pop     rdi
0x100423ffb  retn
```
