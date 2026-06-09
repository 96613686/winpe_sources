# RequestNotification(ulong,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000268c`
- end: `0x1800027d5`
- name: `?RequestNotification@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001a30`
- `0x180001bb0`
- `0x1800024f0`

## callees

- `0x18000268c`
- `0x180003578`
- `0x180003730`
- `0x180006010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000275c`
- `iisutil!PuDbgPrint` at `0x18000275c`

## string_xrefs

- `0x180002755`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\module.cxx`

## pseudocode

```c
__int64 __fastcall RequestNotification(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rax
  _QWORD v9[7]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v10; // [rsp+90h] [rbp+18h] BYREF

  v10 = 0;
  v9[0] = 0;
  if ( (*(int (__fastcall **)(struct IHttpServer *, _QWORD, _QWORD *))(*(_QWORD *)g_pServer + 200LL))(g_pServer, 0, v9) < 0
    || (*(int (__fastcall **)(_QWORD, GUID *, __int64, GUID *, __int64 *))(*(_QWORD *)v9[0] + 224LL))(
         v9[0],
         &GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5,
         a2,
         &GUID_bf53c022_ca4b_4349_a38e_a4b78ad897fb,
         &v10) < 0 )
  {
    goto LABEL_7;
  }
  if ( a1 == 1 )
    return DoBeginRequest(v10, a4);
  if ( a1 != 0x20000000 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\module.cxx",
        266,
        "RequestNotification",
        "Unexpected notification type 0x%08x\r\n",
        a1);
LABEL_7:
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v7 + 24LL))(v7, 500, "Server Error");
    return 2;
  }
  return DoSendResponse(v10);
}

```

## disassembly

```asm
0x18000268c  mov     r11, rsp
0x18000268f  mov     [r11+18h], r8
0x180002693  push    rbx
0x180002694  push    rsi
0x180002695  push    rdi
0x180002696  push    r14
0x180002698  sub     rsp, 58h
0x18000269c  mov     edi, ecx
0x18000269e  mov     qword ptr [r11+18h], 0
0x1800026a6  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x1800026ad  lea     r8, [r11-38h]
0x1800026b1  mov     r14, rdx
0x1800026b4  mov     qword ptr [r11-38h], 0
0x1800026bc  xor     edx, edx
0x1800026be  mov     rsi, r9
0x1800026c1  mov     rax, [rcx]
0x1800026c4  mov     rax, [rax+0C8h]
0x1800026cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d0  mov     ebx, eax
0x1800026d2  test    eax, eax
0x1800026d4  js      loc_180002767
0x1800026da  mov     rcx, [rsp+78h+var_38]
0x1800026df  lea     rdx, [rsp+78h+arg_10]
0x1800026e7  mov     [rsp+78h+var_58], rdx
0x1800026ec  lea     r9, _GUID_bf53c022_ca4b_4349_a38e_a4b78ad897fb
0x1800026f3  mov     r8, r14
0x1800026f6  lea     rdx, _GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5
0x1800026fd  mov     rax, [rcx]
0x180002700  mov     rax, [rax+0E0h]
0x180002707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270c  mov     ebx, eax
0x18000270e  test    eax, eax
0x180002710  js      short loc_180002767
0x180002712  mov     eax, edi
0x180002714  sub     eax, 1
0x180002717  jz      loc_1800027C3
0x18000271d  cmp     eax, 1FFFFFFFh
0x180002722  jz      loc_1800027B4
0x180002728  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000272f  jz      short loc_180002762
0x180002731  mov     rcx, cs:g_pDebug
0x180002738  lea     rax, aUnexpectedNoti; "Unexpected notification type 0x%08x\r\n"
0x18000273f  mov     dword ptr [rsp+78h+var_50], edi
0x180002743  lea     r9, aRequestnotific; "RequestNotification"
0x18000274a  mov     r8d, 10Ah
0x180002750  mov     [rsp+78h+var_58], rax
0x180002755  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000275c  call    cs:__imp_PuDbgPrint
0x180002762  mov     ebx, 8000FFFFh
0x180002767  mov     rax, [r14]
0x18000276a  mov     rcx, r14
0x18000276d  mov     rax, [rax+20h]
0x180002771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002776  xor     r9d, r9d
0x180002779  lea     r8, aServerError; "Server Error"
0x180002780  mov     r10, rax
0x180002783  mov     [rsp+78h+var_48], r9d
0x180002788  mov     [rsp+78h+var_50], r9
0x18000278d  mov     edx, 1F4h
0x180002792  mov     rcx, [rax]
0x180002795  mov     dword ptr [rsp+78h+var_58], ebx
0x180002799  mov     rax, [rcx+18h]
0x18000279d  mov     rcx, r10
0x1800027a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a5  mov     eax, 2
0x1800027aa  add     rsp, 58h
0x1800027ae  pop     r14
0x1800027b0  pop     rdi
0x1800027b1  pop     rsi
0x1800027b2  pop     rbx
0x1800027b3  retn
0x1800027b4  mov     rcx, [rsp+78h+arg_10]
0x1800027bc  call    ?DoSendResponse@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@@Z; DoSendResponse(IHttpContext3 *)
0x1800027c1  jmp     short loc_1800027AA
0x1800027c3  mov     rcx, [rsp+78h+arg_10]
0x1800027cb  mov     rdx, rsi
0x1800027ce  call    ?DoBeginRequest@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo@@@Z; DoBeginRequest(IHttpContext3 *,IHttpCompletionInfo *)
0x1800027d3  jmp     short loc_1800027AA
```
