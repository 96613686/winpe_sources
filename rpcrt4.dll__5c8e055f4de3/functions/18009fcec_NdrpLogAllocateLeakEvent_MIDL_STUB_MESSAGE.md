# NdrpLogAllocateLeakEvent(_MIDL_STUB_MESSAGE *)

- ea: `0x18009fcec`
- end: `0x18009fd98`
- name: `?NdrpLogAllocateLeakEvent@@YAXPEAU_MIDL_STUB_MESSAGE@@@Z`
- size: `172`
- prototype: `void __fastcall(struct _MIDL_STUB_MESSAGE *)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800082d0`
- `0x180039c40`
- `0x18003a260`
- `0x18003c890`
- `0x18003ce70`
- `0x18003d740`
- `0x18003e460`
- `0x1800bdd70`

## callees

- `0x18009fcec`
- `0x1800c011c`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x18009fd37`
- `ntdll!RtlIntegerToUnicodeString` at `0x18009fd37`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18009fd5d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18009fd5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009fd28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009fd28`

## pseudocode

```c
void __fastcall NdrpLogAllocateLeakEvent(struct _MIDL_STUB_MESSAGE *a1)
{
  ULONG CurrentProcessId; // eax
  PRPC_MESSAGE RpcMsg; // rcx
  char ProcNum; // bl
  unsigned int CommandLineW; // eax
  int v6; // edx
  int v7; // ecx
  struct _UNICODE_STRING String; // [rsp+30h] [rbp-48h] BYREF
  __int128 v9; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v10[24]; // [rsp+50h] [rbp-28h] BYREF

  if ( !byte_1800FA465 )
  {
    *(_QWORD *)&String.Length = 1441792;
    v9 = 0;
    String.Buffer = (PWSTR)v10;
    CurrentProcessId = GetCurrentProcessId();
    RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
    RpcMsg = a1->RpcMsg;
    v9 = *(_OWORD *)((char *)a1->RpcMsg->RpcInterfaceInformation + 4);
    if ( (Microsoft_Windows_RPC_EventsEnableBits & 2) != 0 )
    {
      ProcNum = RpcMsg->ProcNum;
      CommandLineW = (unsigned int)GetCommandLineW();
      McTemplateU0zzjd_EtwEventWriteTransfer(v7, v6, CommandLineW, (unsigned int)v10, (__int64)&v9, ProcNum);
    }
    byte_1800FA465 = 1;
  }
}

```

## disassembly

```asm
0x18009fcec  push    rbx
0x18009fcee  sub     rsp, 70h
0x18009fcf2  mov     rax, cs:__security_cookie
0x18009fcf9  xor     rax, rsp
0x18009fcfc  mov     [rsp+78h+var_10], rax
0x18009fd01  cmp     cs:byte_1800FA465, 0
0x18009fd08  mov     rbx, rcx
0x18009fd0b  jnz     short loc_18009FD85
0x18009fd0d  xorps   xmm0, xmm0
0x18009fd10  mov     qword ptr [rsp+78h+String.Length], 160000h
0x18009fd19  lea     rax, [rsp+78h+var_28]
0x18009fd1e  movups  [rsp+78h+var_38], xmm0
0x18009fd23  mov     [rsp+78h+String.Buffer], rax
0x18009fd28  call    cs:__imp_GetCurrentProcessId
0x18009fd2e  lea     r8, [rsp+78h+String]; String
0x18009fd33  xor     edx, edx; Base
0x18009fd35  mov     ecx, eax; Value
0x18009fd37  call    cs:__imp_RtlIntegerToUnicodeString
0x18009fd3d  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 2
0x18009fd44  mov     rcx, [rbx]
0x18009fd47  mov     rax, [rcx+28h]
0x18009fd4b  movups  xmm0, xmmword ptr [rax+4]
0x18009fd4f  movdqu  [rsp+78h+var_38], xmm0
0x18009fd55  jz      short loc_18009FD7E
0x18009fd57  mov     ebx, [rcx+1Ch]
0x18009fd5a  movzx   ebx, bx
0x18009fd5d  call    cs:__imp_GetCommandLineW
0x18009fd63  mov     [rsp+78h+var_50], ebx
0x18009fd67  lea     r9, [rsp+78h+var_28]
0x18009fd6c  mov     r8, rax
0x18009fd6f  lea     rax, [rsp+78h+var_38]
0x18009fd74  mov     [rsp+78h+var_58], rax
0x18009fd79  call    McTemplateU0zzjd_EtwEventWriteTransfer
0x18009fd7e  mov     cs:byte_1800FA465, 1
0x18009fd85  mov     rcx, [rsp+78h+var_10]
0x18009fd8a  xor     rcx, rsp; StackCookie
0x18009fd8d  call    __security_check_cookie
0x18009fd92  add     rsp, 70h
0x18009fd96  pop     rbx
0x18009fd97  retn
```
