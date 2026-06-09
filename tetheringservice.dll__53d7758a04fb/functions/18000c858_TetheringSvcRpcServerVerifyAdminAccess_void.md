# TetheringSvcRpcServerVerifyAdminAccess(void)

- ea: `0x18000c858`
- end: `0x18000c909`
- name: `?TetheringSvcRpcServerVerifyAdminAccess@@YAKXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ccc0`
- `0x18000ce60`
- `0x18000cf90`

## callees

- `0x18000c2cc`
- `0x18000c4f4`
- `0x18000c858`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000c8e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000c8e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8f7`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x18000c865`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x18000c865`

## pseudocode

```c
__int64 TetheringSvcRpcServerVerifyAdminAccess(void)
{
  int v0; // eax
  unsigned int PackageSidStringForToken; // ebx
  LPCWCH lpString1; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v0 = RpcClientCapabilityCheck(L"ID_CAP_ICS_RW");
  if ( (v0 & 0x1FFF0000) == 0x70000 )
    v0 = (unsigned __int16)v0;
  if ( v0 )
  {
    TokenHandle = 0;
    PackageSidStringForToken = LocalQueryRpcClientToken(&TokenHandle);
    if ( !PackageSidStringForToken )
    {
      lpString1 = 0;
      PackageSidStringForToken = GetPackageSidStringForToken(TokenHandle, (LPWSTR *)&lpString1);
      if ( (PackageSidStringForToken & 0x1FFF0000) == 0x70000 )
        PackageSidStringForToken = (unsigned __int16)PackageSidStringForToken;
      if ( !PackageSidStringForToken )
      {
        PackageSidStringForToken = CompareStringOrdinal(
                                     lpString1,
                                     -1,
                                     L"S-1-15-2-155514346-2573954481-755741238-1654018636-1233331829-3075935687-2861478708",
                                     -1,
                                     1) != 2
                                 ? 5
                                 : 0;
        LocalFree((HLOCAL)lpString1);
      }
    }
  }
  else
  {
    return 0;
  }
  return PackageSidStringForToken;
}

```

## disassembly

```asm
0x18000c858  push    rbx
0x18000c85a  sub     rsp, 30h
0x18000c85e  lea     rcx, aIdCapIcsRw; "ID_CAP_ICS_RW"
0x18000c865  call    cs:__imp_RpcClientCapabilityCheck
0x18000c86b  mov     ecx, eax
0x18000c86d  and     ecx, 1FFF0000h
0x18000c873  cmp     ecx, 70000h
0x18000c879  jnz     short loc_18000C87E
0x18000c87b  movzx   eax, ax
0x18000c87e  test    eax, eax
0x18000c880  jz      short loc_18000C8FF
0x18000c882  lea     rcx, [rsp+38h+TokenHandle]; void **
0x18000c887  mov     [rsp+38h+TokenHandle], 0
0x18000c890  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18000c895  mov     ebx, eax
0x18000c897  test    eax, eax
0x18000c899  jnz     short loc_18000C901
0x18000c89b  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18000c8a0  lea     rdx, [rsp+38h+lpString1]; StringSid
0x18000c8a5  mov     [rsp+38h+lpString1], 0
0x18000c8ae  call    ?GetPackageSidStringForToken@@YAJPEAXPEAPEAG@Z; GetPackageSidStringForToken(void *,ushort * *)
0x18000c8b3  mov     ebx, eax
0x18000c8b5  and     eax, 1FFF0000h
0x18000c8ba  cmp     eax, 70000h
0x18000c8bf  jnz     short loc_18000C8C4
0x18000c8c1  movzx   ebx, bx
0x18000c8c4  test    ebx, ebx
0x18000c8c6  jnz     short loc_18000C901
0x18000c8c8  mov     rcx, [rsp+38h+lpString1]; lpString1
0x18000c8cd  lea     r8, String2; "S-1-15-2-155514346-2573954481-755741238"...
0x18000c8d4  or      edx, 0FFFFFFFFh; cchCount1
0x18000c8d7  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000c8df  mov     r9d, edx; cchCount2
0x18000c8e2  call    cs:__imp_CompareStringOrdinal
0x18000c8e8  mov     rcx, [rsp+38h+lpString1]; hMem
0x18000c8ed  sub     eax, 2
0x18000c8f0  neg     eax
0x18000c8f2  sbb     ebx, ebx
0x18000c8f4  and     ebx, 5
0x18000c8f7  call    cs:__imp_LocalFree
0x18000c8fd  jmp     short loc_18000C901
0x18000c8ff  xor     ebx, ebx
0x18000c901  mov     eax, ebx
0x18000c903  add     rsp, 30h
0x18000c907  pop     rbx
0x18000c908  retn
```
