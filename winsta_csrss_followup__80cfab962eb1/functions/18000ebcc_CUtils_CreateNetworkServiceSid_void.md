# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x18000ebcc`
- end: `0x18000ec83`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000eb30`

## callees

- `0x180005b40`
- `0x18000ebcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ebe7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ebe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec36`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ec08`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ec08`

## string_xrefs

- `0x18000ec66`: `CUtils::CreateNetworkServiceSid`
- `0x18000ec70`: `new pLocalNetworkServiceSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateNetworkServiceSid(void **a1)
{
  HLOCAL v1; // rax
  void *v2; // rdi
  signed int v3; // ebx
  signed int LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+34h] [rbp+Ch]

  v7 = HIDWORD(a1);
  cbSid = 68;
  v1 = LocalAlloc(0x40u, 0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinNetworkServiceSid, 0, v1, &cbSid) )
    {
      CPublicBinding::pNetsrvSid = v2;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
        LocalFree(v2);
    }
  }
  else
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "new pLocalNetworkServiceSid failed: 0x%x in %s",
      -2147024882,
      "CUtils::CreateNetworkServiceSid");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ebcc  mov     [rsp+arg_8], rbx
0x18000ebd1  mov     qword ptr [rsp+cbSid], rcx
0x18000ebd6  push    rdi
0x18000ebd7  sub     rsp, 20h
0x18000ebdb  mov     edx, 44h ; 'D'; uBytes
0x18000ebe0  mov     [rsp+28h+cbSid], edx
0x18000ebe4  lea     ecx, [rdx-4]; uFlags
0x18000ebe7  call    cs:__imp_LocalAlloc
0x18000ebee  nop     dword ptr [rax+rax+00h]
0x18000ebf3  mov     rdi, rax
0x18000ebf6  test    rax, rax
0x18000ebf9  jz      short loc_18000EC61
0x18000ebfb  xor     edx, edx; DomainSid
0x18000ebfd  lea     r9, [rsp+28h+cbSid]; cbSid
0x18000ec02  mov     r8, rax; pSid
0x18000ec05  lea     ecx, [rdx+18h]; WellKnownSidType
0x18000ec08  call    cs:__imp_CreateWellKnownSid
0x18000ec0f  nop     dword ptr [rax+rax+00h]
0x18000ec14  test    eax, eax
0x18000ec16  jz      short loc_18000EC44
0x18000ec18  mov     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, rdi; void * CPublicBinding::pNetsrvSid
0x18000ec1f  xor     ebx, ebx
0x18000ec21  mov     eax, ebx
0x18000ec23  mov     rbx, [rsp+28h+arg_8]
0x18000ec28  add     rsp, 20h
0x18000ec2c  pop     rdi
0x18000ec2d  retn
0x18000ec2f  test    ebx, ebx
0x18000ec31  jns     short loc_18000EC21
0x18000ec33  mov     rcx, rdi; hMem
0x18000ec36  call    cs:__imp_LocalFree
0x18000ec3d  nop     dword ptr [rax+rax+00h]
0x18000ec42  jmp     short loc_18000EC21
0x18000ec44  call    cs:__imp_GetLastError
0x18000ec4b  nop     dword ptr [rax+rax+00h]
0x18000ec50  mov     ebx, eax
0x18000ec52  test    eax, eax
0x18000ec54  jle     short loc_18000EC2F
0x18000ec56  movzx   ebx, ax
0x18000ec59  or      ebx, 80070000h
0x18000ec5f  jmp     short loc_18000EC2F
0x18000ec61  mov     ebx, 8007000Eh
0x18000ec66  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x18000ec6d  mov     r8d, ebx
0x18000ec70  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x18000ec77  mov     ecx, 8; int
0x18000ec7c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ec81  jmp     short loc_18000EC21
```
