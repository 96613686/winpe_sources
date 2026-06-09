# NdrpLogAllocateLeakEvent(_MIDL_STUB_MESSAGE *)

- ea: `0x1800a330c`
- end: `0x1800a33cf`
- name: `?NdrpLogAllocateLeakEvent@@YAXPEAU_MIDL_STUB_MESSAGE@@@Z`
- size: `195`
- prototype: `void __fastcall(struct _MIDL_STUB_MESSAGE *)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003a810`
- `0x18004a250`
- `0x18004a880`
- `0x18004cf10`
- `0x18004d500`
- `0x18004ddd0`
- `0x18004eaf0`
- `0x1800c2520`

## callees

- `0x1800a330c`
- `0x1800c4934`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x1800a3361`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800a3361`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a338d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a338d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a334c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a334c`

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

  if ( !byte_1800FF465 )
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
    byte_1800FF465 = 1;
  }
}

```

## disassembly

```asm
0x1800a330c  push    rbx
0x1800a330e  sub     rsp, 70h
0x1800a3312  mov     rax, cs:__security_cookie
0x1800a3319  xor     rax, rsp
0x1800a331c  mov     [rsp+78h+var_10], rax
0x1800a3321  cmp     cs:byte_1800FF465, 0
0x1800a3328  mov     rbx, rcx
0x1800a332b  jnz     loc_1800A33BB
0x1800a3331  xorps   xmm0, xmm0
0x1800a3334  mov     qword ptr [rsp+78h+String.Length], 160000h
0x1800a333d  lea     rax, [rsp+78h+var_28]
0x1800a3342  movups  [rsp+78h+var_38], xmm0
0x1800a3347  mov     [rsp+78h+String.Buffer], rax
0x1800a334c  call    cs:__imp_GetCurrentProcessId
0x1800a3353  nop     dword ptr [rax+rax+00h]
0x1800a3358  lea     r8, [rsp+78h+String]; String
0x1800a335d  xor     edx, edx; Base
0x1800a335f  mov     ecx, eax; Value
0x1800a3361  call    cs:__imp_RtlIntegerToUnicodeString
0x1800a3368  nop     dword ptr [rax+rax+00h]
0x1800a336d  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 2
0x1800a3374  mov     rcx, [rbx]
0x1800a3377  mov     rax, [rcx+28h]
0x1800a337b  movups  xmm0, xmmword ptr [rax+4]
0x1800a337f  movdqu  [rsp+78h+var_38], xmm0
0x1800a3385  jz      short loc_1800A33B4
0x1800a3387  mov     ebx, [rcx+1Ch]
0x1800a338a  movzx   ebx, bx
0x1800a338d  call    cs:__imp_GetCommandLineW
0x1800a3394  nop     dword ptr [rax+rax+00h]
0x1800a3399  mov     [rsp+78h+var_50], ebx
0x1800a339d  lea     r9, [rsp+78h+var_28]
0x1800a33a2  mov     r8, rax
0x1800a33a5  lea     rax, [rsp+78h+var_38]
0x1800a33aa  mov     [rsp+78h+var_58], rax
0x1800a33af  call    McTemplateU0zzjd_EtwEventWriteTransfer
0x1800a33b4  mov     cs:byte_1800FF465, 1
0x1800a33bb  mov     rcx, [rsp+78h+var_10]
0x1800a33c0  xor     rcx, rsp; StackCookie
0x1800a33c3  call    __security_check_cookie
0x1800a33c8  add     rsp, 70h
0x1800a33cc  pop     rbx
0x1800a33cd  retn
```
