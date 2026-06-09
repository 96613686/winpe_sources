# RSCA_WORKITEM::ExecuteWorkItem(void)

- ea: `0x18000b1d0`
- end: `0x18000b360`
- name: `?ExecuteWorkItem@RSCA_WORKITEM@@UEAAXXZ`
- size: `400`
- prototype: `void __fastcall(RSCA_WORKITEM *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800010c0`
- `0x180001970`
- `0x180001f68`
- `0x18000b1d0`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b1ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b29f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2ac`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b315`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b1ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b29f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2ac`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b315`
- `iisutil!PuDbgPrint` at `0x18000b221`
- `iisutil!PuDbgPrint` at `0x18000b34b`
- `iisutil!PuDbgPrint` at `0x18000b221`
- `iisutil!PuDbgPrint` at `0x18000b34b`

## string_xrefs

- `0x18000b208`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\rsca_workitem.cxx`
- `0x18000b32d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\rsca_workitem.cxx`

## pseudocode

```c
void __fastcall RSCA_WORKITEM::ExecuteWorkItem(RSCA_WORKITEM *this)
{
  char *v2; // r14
  unsigned int v3; // eax
  PROTOCOL_MANAGER_LIST *v4; // r15
  int v5; // ebx
  struct PROTOCOL_MANAGER_ENTRY *i; // rdx
  struct PROTOCOL_MANAGER_ENTRY *NextProtocolManagerEntry; // rax
  struct PROTOCOL_MANAGER_ENTRY *v8; // r13
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, unsigned __int16 *, unsigned __int16 *, char *); // rdi
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v12; // rax
  W3WP_HOST *v13; // rcx
  __int64 v14; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\rsca_workitem.cxx",
      162,
      "RSCA_WORKITEM::ExecuteWorkItem",
      "Process Model Requesting WP Data called for %S \n");
  }
  v2 = (char *)operator new(0x18u);
  if ( !v2 )
    goto LABEL_14;
  v3 = *((_DWORD *)this + 12);
  _InterlockedIncrement(&CALLBACK_BASE::sm_CallbackInstanceCount);
  *((_DWORD *)v2 + 2) = 1;
  *(_QWORD *)v2 = &CUSTOM_ACTION_CALLBACK::`vftable';
  *(_QWORD *)(v2 + 12) = v3;
  v4 = (PROTOCOL_MANAGER_LIST *)(*((_QWORD *)this + 5) + 320LL);
  if ( *((_QWORD *)this + 5) == -320 )
  {
    v5 = -2147418113;
  }
  else
  {
    v5 = 0;
    for ( i = 0; ; i = v8 )
    {
      NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(v4, i);
      v8 = NextProtocolManagerEntry;
      if ( !NextProtocolManagerEntry )
        break;
      v9 = *((_QWORD *)NextProtocolManagerEntry + 33);
      v10 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, char *))(*(_QWORD *)v9 + 16LL);
      Str = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 112));
      v12 = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
      v5 = v10(v9, v12, Str, v2);
      if ( v5 != -2147467263 )
      {
        v13 = (W3WP_HOST *)*((_QWORD *)this + 5);
        v14 = *((_QWORD *)v13 + 12);
        if ( v14 && *(_DWORD *)(v14 + 24) )
          W3WP_HOST::IncrementMessages(v13, 0);
        break;
      }
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v5 < 0 )
  {
LABEL_14:
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\rsca_workitem.cxx",
        241,
        "RSCA_WORKITEM::ExecuteWorkItem",
        "CustomAction call %S failed with error 0x%x \n");
    }
  }
}

```

## disassembly

```asm
0x18000b1d0  push    rbx
0x18000b1d2  push    rbp
0x18000b1d3  push    rsi
0x18000b1d4  push    rdi
0x18000b1d5  push    r13
0x18000b1d7  push    r14
0x18000b1d9  push    r15
0x18000b1db  sub     rsp, 40h
0x18000b1df  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b1e6  mov     rbp, rcx
0x18000b1e9  jz      short loc_18000B227
0x18000b1eb  add     rcx, 38h ; '8'
0x18000b1ef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b1f5  mov     rcx, cs:g_pDebug
0x18000b1fc  lea     r9, aRscaWorkitemEx; "RSCA_WORKITEM::ExecuteWorkItem"
0x18000b203  mov     [rsp+78h+var_50], rax
0x18000b208  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b20f  lea     rax, aProcessModelRe; "Process Model Requesting WP Data called"...
0x18000b216  mov     r8d, 0A2h
0x18000b21c  mov     [rsp+78h+var_58], rax
0x18000b221  call    cs:__imp_PuDbgPrint
0x18000b227  mov     ecx, 18h; Size
0x18000b22c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b231  mov     r14, rax
0x18000b234  test    rax, rax
0x18000b237  jz      loc_18000B303
0x18000b23d  mov     eax, [rbp+30h]
0x18000b240  lock inc cs:?sm_CallbackInstanceCount@CALLBACK_BASE@@0JA; long CALLBACK_BASE::sm_CallbackInstanceCount
0x18000b247  lea     rcx, ??_7CUSTOM_ACTION_CALLBACK@@6B@; const CUSTOM_ACTION_CALLBACK::`vftable'
0x18000b24e  mov     dword ptr [r14+8], 1
0x18000b256  mov     [r14], rcx
0x18000b259  mov     [r14+0Ch], eax
0x18000b25d  mov     dword ptr [r14+10h], 0
0x18000b265  mov     r15, [rbp+28h]
0x18000b269  add     r15, 140h
0x18000b270  jnz     short loc_18000B279
0x18000b272  mov     ebx, 8000FFFFh
0x18000b277  jmp     short loc_18000B2EE
0x18000b279  xor     ebx, ebx
0x18000b27b  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x18000b27d  mov     rcx, r15; this
0x18000b280  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x18000b285  mov     r13, rax
0x18000b288  test    rax, rax
0x18000b28b  jz      short loc_18000B2EE
0x18000b28d  mov     rsi, [rax+108h]
0x18000b294  lea     rcx, [rbp+70h]
0x18000b298  mov     rdx, [rsi]
0x18000b29b  mov     rdi, [rdx+10h]
0x18000b29f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b2a5  lea     rcx, [rbp+38h]
0x18000b2a9  mov     rbx, rax
0x18000b2ac  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b2b2  mov     r9, r14
0x18000b2b5  mov     r8, rbx
0x18000b2b8  mov     rdx, rax
0x18000b2bb  mov     rcx, rsi
0x18000b2be  mov     rax, rdi
0x18000b2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c6  mov     ebx, eax
0x18000b2c8  cmp     eax, 80004001h
0x18000b2cd  jnz     short loc_18000B2D4
0x18000b2cf  mov     rdx, r13
0x18000b2d2  jmp     short loc_18000B27D
0x18000b2d4  mov     rcx, [rbp+28h]; this
0x18000b2d8  mov     rax, [rcx+60h]
0x18000b2dc  test    rax, rax
0x18000b2df  jz      short loc_18000B2EE
0x18000b2e1  cmp     dword ptr [rax+18h], 0
0x18000b2e5  jz      short loc_18000B2EE
0x18000b2e7  xor     edx, edx; unsigned int
0x18000b2e9  call    ?IncrementMessages@W3WP_HOST@@QEAAXK@Z; W3WP_HOST::IncrementMessages(ulong)
0x18000b2ee  mov     rax, [r14]
0x18000b2f1  mov     rcx, r14
0x18000b2f4  mov     rax, [rax+8]
0x18000b2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2fd  test    ebx, ebx
0x18000b2ff  jns     short loc_18000B351
0x18000b301  jmp     short loc_18000B308
0x18000b303  mov     ebx, 8007000Eh
0x18000b308  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b30f  jz      short loc_18000B351
0x18000b311  lea     rcx, [rbp+38h]
0x18000b315  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b31b  mov     rcx, cs:g_pDebug
0x18000b322  lea     r9, aRscaWorkitemEx; "RSCA_WORKITEM::ExecuteWorkItem"
0x18000b329  mov     [rsp+78h+var_48], ebx
0x18000b32d  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b334  mov     [rsp+78h+var_50], rax
0x18000b339  mov     r8d, 0F1h
0x18000b33f  lea     rax, aCustomactionCa; "CustomAction call %S failed with error "...
0x18000b346  mov     [rsp+78h+var_58], rax
0x18000b34b  call    cs:__imp_PuDbgPrint
0x18000b351  add     rsp, 40h
0x18000b355  pop     r15
0x18000b357  pop     r14
0x18000b359  pop     r13
0x18000b35b  pop     rdi
0x18000b35c  pop     rsi
0x18000b35d  pop     rbp
0x18000b35e  pop     rbx
0x18000b35f  retn
```
