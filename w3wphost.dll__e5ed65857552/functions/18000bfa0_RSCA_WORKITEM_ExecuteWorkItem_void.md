# RSCA_WORKITEM::ExecuteWorkItem(void)

- ea: `0x18000bfa0`
- end: `0x18000c158`
- name: `?ExecuteWorkItem@RSCA_WORKITEM@@UEAAXXZ`
- size: `440`
- prototype: `void __fastcall(RSCA_WORKITEM *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800010c0`
- `0x1800019f0`
- `0x180002090`
- `0x18000bfa0`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bfbf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c07e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c091`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c100`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bfbf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c07e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c091`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c100`
- `iisutil!PuDbgPrint` at `0x18000bff7`
- `iisutil!PuDbgPrint` at `0x18000c13c`
- `iisutil!PuDbgPrint` at `0x18000bff7`
- `iisutil!PuDbgPrint` at `0x18000c13c`

## string_xrefs

- `0x18000bfde`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\rsca_workitem.cxx`
- `0x18000c11e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\rsca_workitem.cxx`

## pseudocode

```c
void __fastcall RSCA_WORKITEM::ExecuteWorkItem(RSCA_WORKITEM *this)
{
  const wchar_t *Str; // rax
  char *v3; // r14
  unsigned int v4; // eax
  PROTOCOL_MANAGER_LIST *v5; // r15
  int v6; // ebx
  PROTOCOL_MANAGER_ENTRY **i; // rdx
  PROTOCOL_MANAGER_ENTRY **NextProtocolManagerEntry; // rax
  PROTOCOL_MANAGER_ENTRY **v9; // r13
  PROTOCOL_MANAGER_ENTRY *v10; // rsi
  __int64 (__fastcall *v11)(PROTOCOL_MANAGER_ENTRY *, unsigned __int16 *, unsigned __int16 *, char *); // rdi
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rax
  W3WP_HOST *v14; // rcx
  __int64 v15; // rax
  const wchar_t *v16; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    Str = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\rsca_workitem.cxx",
      162,
      "RSCA_WORKITEM::ExecuteWorkItem",
      "Process Model Requesting WP Data called for %S \n",
      Str);
  }
  v3 = (char *)operator new(0x18u);
  if ( !v3 )
  {
    v6 = -2147024882;
LABEL_16:
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v16 = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\rsca_workitem.cxx",
        241,
        "RSCA_WORKITEM::ExecuteWorkItem",
        "CustomAction call %S failed with error 0x%x \n",
        v16,
        v6);
    }
    return;
  }
  v4 = *((_DWORD *)this + 12);
  _InterlockedIncrement(&CALLBACK_BASE::sm_CallbackInstanceCount);
  *((_DWORD *)v3 + 2) = 1;
  *(_QWORD *)v3 = &CUSTOM_ACTION_CALLBACK::`vftable';
  *(_QWORD *)(v3 + 12) = v4;
  v5 = (PROTOCOL_MANAGER_LIST *)(*((_QWORD *)this + 5) + 320LL);
  if ( *((_QWORD *)this + 5) == -320 )
  {
    v6 = -2147418113;
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; i = v9 )
    {
      NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(v5, i);
      v9 = NextProtocolManagerEntry;
      if ( !NextProtocolManagerEntry )
        break;
      v10 = NextProtocolManagerEntry[33];
      v11 = *(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, unsigned __int16 *, unsigned __int16 *, char *))(*(_QWORD *)v10 + 16LL);
      v12 = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 112));
      v13 = STRU::QueryStr((RSCA_WORKITEM *)((char *)this + 56));
      v6 = v11(v10, v13, v12, v3);
      if ( v6 != -2147467263 )
      {
        v14 = (W3WP_HOST *)*((_QWORD *)this + 5);
        v15 = *((_QWORD *)v14 + 12);
        if ( v15 && *(_DWORD *)(v15 + 24) )
          W3WP_HOST::IncrementMessages(v14, 0);
        break;
      }
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v6 < 0 )
    goto LABEL_16;
}

```

## disassembly

```asm
0x18000bfa0  push    rbx
0x18000bfa2  push    rbp
0x18000bfa3  push    rsi
0x18000bfa4  push    rdi
0x18000bfa5  push    r13
0x18000bfa7  push    r14
0x18000bfa9  push    r15
0x18000bfab  sub     rsp, 40h
0x18000bfaf  test    byte ptr cs:g_dwDebugFlags, 3
0x18000bfb6  mov     rbp, rcx
0x18000bfb9  jz      short loc_18000C003
0x18000bfbb  add     rcx, 38h ; '8'
0x18000bfbf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bfc6  nop     dword ptr [rax+rax+00h]
0x18000bfcb  mov     rcx, cs:g_pDebug
0x18000bfd2  lea     r9, aRscaWorkitemEx; "RSCA_WORKITEM::ExecuteWorkItem"
0x18000bfd9  mov     [rsp+78h+var_50], rax
0x18000bfde  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000bfe5  lea     rax, aProcessModelRe; "Process Model Requesting WP Data called"...
0x18000bfec  mov     r8d, 0A2h
0x18000bff2  mov     [rsp+78h+var_58], rax
0x18000bff7  call    cs:__imp_PuDbgPrint
0x18000bffe  nop     dword ptr [rax+rax+00h]
0x18000c003  mov     ecx, 18h; Size
0x18000c008  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c00d  mov     r14, rax
0x18000c010  test    rax, rax
0x18000c013  jz      loc_18000C0EE
0x18000c019  mov     eax, [rbp+30h]
0x18000c01c  lock inc cs:?sm_CallbackInstanceCount@CALLBACK_BASE@@0JA; long CALLBACK_BASE::sm_CallbackInstanceCount
0x18000c023  lea     rcx, ??_7CUSTOM_ACTION_CALLBACK@@6B@; const CUSTOM_ACTION_CALLBACK::`vftable'
0x18000c02a  mov     dword ptr [r14+8], 1
0x18000c032  mov     [r14], rcx
0x18000c035  mov     [r14+0Ch], eax
0x18000c039  mov     dword ptr [r14+10h], 0
0x18000c041  mov     r15, [rbp+28h]
0x18000c045  add     r15, 140h
0x18000c04c  jnz     short loc_18000C058
0x18000c04e  mov     ebx, 8000FFFFh
0x18000c053  jmp     loc_18000C0D9
0x18000c058  xor     ebx, ebx
0x18000c05a  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x18000c05c  mov     rcx, r15; this
0x18000c05f  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x18000c064  mov     r13, rax
0x18000c067  test    rax, rax
0x18000c06a  jz      short loc_18000C0D9
0x18000c06c  mov     rsi, [rax+108h]
0x18000c073  lea     rcx, [rbp+70h]
0x18000c077  mov     rdx, [rsi]
0x18000c07a  mov     rdi, [rdx+10h]
0x18000c07e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c085  nop     dword ptr [rax+rax+00h]
0x18000c08a  lea     rcx, [rbp+38h]
0x18000c08e  mov     rbx, rax
0x18000c091  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c098  nop     dword ptr [rax+rax+00h]
0x18000c09d  mov     r9, r14
0x18000c0a0  mov     r8, rbx
0x18000c0a3  mov     rdx, rax
0x18000c0a6  mov     rcx, rsi
0x18000c0a9  mov     rax, rdi
0x18000c0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b1  mov     ebx, eax
0x18000c0b3  cmp     eax, 80004001h
0x18000c0b8  jnz     short loc_18000C0BF
0x18000c0ba  mov     rdx, r13
0x18000c0bd  jmp     short loc_18000C05C
0x18000c0bf  mov     rcx, [rbp+28h]; this
0x18000c0c3  mov     rax, [rcx+60h]
0x18000c0c7  test    rax, rax
0x18000c0ca  jz      short loc_18000C0D9
0x18000c0cc  cmp     dword ptr [rax+18h], 0
0x18000c0d0  jz      short loc_18000C0D9
0x18000c0d2  xor     edx, edx; unsigned int
0x18000c0d4  call    ?IncrementMessages@W3WP_HOST@@QEAAXK@Z; W3WP_HOST::IncrementMessages(ulong)
0x18000c0d9  mov     rax, [r14]
0x18000c0dc  mov     rcx, r14
0x18000c0df  mov     rax, [rax+8]
0x18000c0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e8  test    ebx, ebx
0x18000c0ea  jns     short loc_18000C148
0x18000c0ec  jmp     short loc_18000C0F3
0x18000c0ee  mov     ebx, 8007000Eh
0x18000c0f3  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c0fa  jz      short loc_18000C148
0x18000c0fc  lea     rcx, [rbp+38h]
0x18000c100  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c107  nop     dword ptr [rax+rax+00h]
0x18000c10c  mov     rcx, cs:g_pDebug
0x18000c113  lea     r9, aRscaWorkitemEx; "RSCA_WORKITEM::ExecuteWorkItem"
0x18000c11a  mov     [rsp+78h+var_48], ebx
0x18000c11e  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000c125  mov     [rsp+78h+var_50], rax
0x18000c12a  mov     r8d, 0F1h
0x18000c130  lea     rax, aCustomactionCa; "CustomAction call %S failed with error "...
0x18000c137  mov     [rsp+78h+var_58], rax
0x18000c13c  call    cs:__imp_PuDbgPrint
0x18000c143  nop     dword ptr [rax+rax+00h]
0x18000c148  add     rsp, 40h
0x18000c14c  pop     r15
0x18000c14e  pop     r14
0x18000c150  pop     r13
0x18000c152  pop     rdi
0x18000c153  pop     rsi
0x18000c154  pop     rbp
0x18000c155  pop     rbx
0x18000c156  retn
```
