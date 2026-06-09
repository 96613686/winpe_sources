# CIISModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001a30`
- end: `0x180001adc`
- name: `?OnAsyncCompletion@CIISModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001a30`
- `0x18000268c`
- `0x180006010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180001a77`
- `iisutil!PuDbgPrint` at `0x180001a77`

## string_xrefs

- `0x180001a52`: `Unexepected comletion for post event 0x%08x\n`
- `0x180001a5e`: `CIISModule::OnAsyncCompletion`
- `0x180001a70`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\module.hxx`

## pseudocode

```c
__int64 __fastcall CIISModule::OnAsyncCompletion(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  __int64 v7; // rax

  if ( !a4 )
    return RequestNotification(a3, a2, a3, a6);
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\module.hxx",
      108,
      "CIISModule::OnAsyncCompletion",
      "Unexepected comletion for post event 0x%08x\r\n",
      a3);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2);
  (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v7 + 24LL))(v7, 500, "Server Error");
  return 2;
}

```

## disassembly

```asm
0x180001a30  push    rbx
0x180001a32  sub     rsp, 40h
0x180001a36  mov     rbx, rdx
0x180001a39  test    r9d, r9d
0x180001a3c  jz      loc_180001ACA
0x180001a42  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001a49  jz      short loc_180001A7D
0x180001a4b  mov     rcx, cs:g_pDebug
0x180001a52  lea     rax, aUnexepectedCom; "Unexepected comletion for post event 0x"...
0x180001a59  mov     dword ptr [rsp+48h+var_20], r8d
0x180001a5e  lea     r9, aCiismoduleOnas; "CIISModule::OnAsyncCompletion"
0x180001a65  mov     r8d, 6Ch ; 'l'
0x180001a6b  mov     [rsp+48h+var_28], rax
0x180001a70  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001a77  call    cs:__imp_PuDbgPrint
0x180001a7d  mov     rax, [rbx]
0x180001a80  mov     rcx, rbx
0x180001a83  mov     rax, [rax+20h]
0x180001a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a8c  xor     r9d, r9d
0x180001a8f  lea     r8, aServerError; "Server Error"
0x180001a96  mov     r10, rax
0x180001a99  mov     [rsp+48h+var_18], r9d
0x180001a9e  mov     [rsp+48h+var_20], r9
0x180001aa3  mov     edx, 1F4h
0x180001aa8  mov     rcx, [rax]
0x180001aab  mov     dword ptr [rsp+48h+var_28], 8000FFFFh
0x180001ab3  mov     rax, [rcx+18h]
0x180001ab7  mov     rcx, r10
0x180001aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001abf  mov     eax, 2
0x180001ac4  add     rsp, 40h
0x180001ac8  pop     rbx
0x180001ac9  retn
0x180001aca  mov     r9, [rsp+48h+arg_28]
0x180001acf  mov     ecx, r8d
0x180001ad2  add     rsp, 40h
0x180001ad6  pop     rbx
0x180001ad7  jmp     ?RequestNotification@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestNotification(ulong,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
