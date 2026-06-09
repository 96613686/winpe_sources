# WinStationShadowStop2

- ea: `0x1800216a0`
- end: `0x180021799`
- name: `WinStationShadowStop2`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800216a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021776`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021776`
- `RPCRT4!NdrClientCall3` at `0x180021712`
- `RPCRT4!NdrClientCall3` at `0x180021712`

## string_xrefs

- `0x1800216cb`: `Failed to open binding`

## pseudocode

```c
char WinStationShadowStop2()
{
  char v0; // di
  ULONG SessionId; // ebx
  void *v2; // rax
  int Pointer; // ebx
  DWORD v4; // eax
  ULONG v6; // [rsp+20h] [rbp-38h]
  unsigned __int16 v7[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 1);
  v0 = 0;
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    SessionId = NtCurrentPeb()->SessionId;
    v2 = CSmartPublicBinding::operator void *(v7);
    v6 = SessionId;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 0xAu, 0, v2, v6).Pointer;
    if ( Pointer >= 0 )
    {
      v0 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcShadowStop2 failed: 0x%x in %s", Pointer, "WinStationShadowStop2");
      v4 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v4);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v0;
}

```

## disassembly

```asm
0x1800216a0  mov     [rsp+arg_8], rbx
0x1800216a5  push    rdi
0x1800216a6  sub     rsp, 50h
0x1800216aa  xor     edx, edx; void *
0x1800216ac  lea     r8d, [rdx+1]; int
0x1800216b0  lea     rcx, [rsp+58h+var_20]; this
0x1800216b5  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800216ba  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800216bf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800216c4  xor     edi, edi
0x1800216c6  test    rax, rax
0x1800216c9  jnz     short loc_1800216DF
0x1800216cb  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800216d2  lea     ecx, [rdi+8]; int
0x1800216d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800216da  jmp     loc_180021781
0x1800216df  mov     rax, gs:60h
0x1800216e8  mov     ebx, [rax+2C0h]
0x1800216ee  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800216f3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800216f8  mov     [rsp+58h+arg_0], rdi
0x1800216fd  mov     [rsp+58h+var_38], ebx
0x180021701  mov     r9, rax
0x180021704  xor     r8d, r8d; pReturnValue
0x180021707  lea     edx, [r8+0Ah]; nProcNum
0x18002170b  lea     rcx, stru_180032140; pProxyInfo
0x180021712  call    cs:__imp_NdrClientCall3
0x180021718  mov     rbx, rax
0x18002171b  mov     [rsp+58h+arg_0], rax
0x180021720  mov     [rsp+58h+var_28], eax
0x180021724  jmp     short loc_18002174E
0x180021726  test    eax, eax
0x180021728  jle     short loc_180021732
0x18002172a  movzx   eax, ax
0x18002172d  or      eax, 80070000h
0x180021732  mov     ebx, eax
0x180021734  mov     [rsp+58h+var_28], eax
0x180021738  mov     r8d, eax
0x18002173b  lea     rdx, aRpcshadowstop2_0; "RpcShadowStop2 threw an exception: 0x%x"
0x180021742  mov     ecx, 8; int
0x180021747  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002174c  xor     edi, edi
0x18002174e  test    ebx, ebx
0x180021750  jns     short loc_18002177E
0x180021752  lea     r9, aWinstationshad_6; "WinStationShadowStop2"
0x180021759  mov     r8d, ebx
0x18002175c  lea     rdx, aRpcshadowstop2; "RpcShadowStop2 failed: 0x%x in %s"
0x180021763  mov     ecx, 8; int
0x180021768  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002176d  mov     ecx, ebx; int
0x18002176f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021774  mov     ecx, eax; dwErrCode
0x180021776  call    cs:__imp_SetLastError
0x18002177c  jmp     short loc_180021781
0x18002177e  mov     dil, 1
0x180021781  lea     rcx, [rsp+58h+var_20]; this
0x180021786  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002178b  mov     al, dil
0x18002178e  mov     rbx, [rsp+58h+arg_8]
0x180021793  add     rsp, 50h
0x180021797  pop     rdi
0x180021798  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
