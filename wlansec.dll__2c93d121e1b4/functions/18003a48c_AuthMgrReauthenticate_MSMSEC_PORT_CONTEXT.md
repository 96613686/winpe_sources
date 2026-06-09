# AuthMgrReauthenticate(MSMSEC_PORT_CONTEXT *)

- ea: `0x18003a48c`
- end: `0x18003a5d1`
- name: `?AuthMgrReauthenticate@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `325`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180057874`
- `0x180063390`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x18003a48c`
- `0x18003a5d8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18003a557`
- `MobileNetworking!ReleaseWriteLock` at `0x18003a557`
- `MobileNetworking!AcquireWriteLock` at `0x18003a4fd`
- `MobileNetworking!AcquireWriteLock` at `0x18003a4fd`

## pseudocode

```c
__int64 __fastcall AuthMgrReauthenticate(struct MSMSEC_PORT_CONTEXT *a1)
{
  unsigned int v2; // ebx
  PVOID *v3; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 128, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "AuthMgrReauthenticate", 1443);
  v2 = AuthMgrRedoSecurity(
         (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920),
         *(struct DOT11_MSMSEC_CONNECTION_PROFILE **)(*((_QWORD *)a1 + 3) + 2784LL),
         *(struct DOT11_MSMSEC_RUNTIME_STATE **)(*((_QWORD *)a1 + 3) + 2904LL));
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "AuthMgrReauthenticate", 1451);
  if ( !v2 )
    goto LABEL_8;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 129, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v2);
LABEL_8:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x100) != 0 )
    WPP_SF_d(v3[7], 130, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18003a48c  mov     [rsp+arg_0], rbx
0x18003a491  mov     [rsp+arg_8], rsi
0x18003a496  push    rdi
0x18003a497  sub     rsp, 20h
0x18003a49b  mov     rdi, rcx
0x18003a49e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4a5  lea     rsi, WPP_GLOBAL_Control
0x18003a4ac  cmp     rcx, rsi
0x18003a4af  jz      short loc_18003A4CF
0x18003a4b1  test    dword ptr [rcx+44h], 100h
0x18003a4b8  jz      short loc_18003A4CF
0x18003a4ba  mov     rcx, [rcx+38h]
0x18003a4be  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x18003a4c5  mov     edx, 80h
0x18003a4ca  call    WPP_SF_
0x18003a4cf  mov     rcx, [rdi+18h]
0x18003a4d3  lea     rdx, aLocking; ">>> Locking >>>"
0x18003a4da  mov     ecx, [rcx+9C0h]; unsigned int
0x18003a4e0  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003a4e5  mov     rcx, [rdi+18h]
0x18003a4e9  lea     r8, aAuthmgrreauthe; "AuthMgrReauthenticate"
0x18003a4f0  mov     r9d, 5A3h
0x18003a4f6  lea     rdx, [rcx+9D0h]
0x18003a4fd  call    cs:__imp_AcquireWriteLock
0x18003a504  nop     dword ptr [rax+rax+00h]
0x18003a509  mov     rdx, [rdi+18h]
0x18003a50d  lea     rcx, [rdi+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x18003a514  mov     r8, [rdx+0B58h]; struct DOT11_MSMSEC_RUNTIME_STATE *
0x18003a51b  mov     rdx, [rdx+0AE0h]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18003a522  call    ?AuthMgrRedoSecurity@@YAKPEAUMSMSEC_PORT_AUTH_CONTEXT@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z; AuthMgrRedoSecurity(MSMSEC_PORT_AUTH_CONTEXT *,DOT11_MSMSEC_CONNECTION_PROFILE *,DOT11_MSMSEC_RUNTIME_STATE *)
0x18003a527  mov     rcx, [rdi+18h]
0x18003a52b  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003a532  mov     ebx, eax
0x18003a534  mov     ecx, [rcx+9C0h]; unsigned int
0x18003a53a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003a53f  mov     rcx, [rdi+18h]
0x18003a543  lea     r8, aAuthmgrreauthe; "AuthMgrReauthenticate"
0x18003a54a  mov     r9d, 5ABh
0x18003a550  lea     rdx, [rcx+9D0h]
0x18003a557  call    cs:__imp_ReleaseWriteLock
0x18003a55e  nop     dword ptr [rax+rax+00h]
0x18003a563  test    ebx, ebx
0x18003a565  jz      short loc_18003A591
0x18003a567  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a56e  cmp     rcx, rsi
0x18003a571  jz      short loc_18003A5BE
0x18003a573  test    byte ptr [rcx+44h], 1
0x18003a577  jz      short loc_18003A598
0x18003a579  mov     rcx, [rcx+38h]
0x18003a57d  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x18003a584  mov     edx, 81h
0x18003a589  mov     r9d, ebx
0x18003a58c  call    WPP_SF_d
0x18003a591  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a598  cmp     rcx, rsi
0x18003a59b  jz      short loc_18003A5BE
0x18003a59d  test    dword ptr [rcx+44h], 100h
0x18003a5a4  jz      short loc_18003A5BE
0x18003a5a6  mov     rcx, [rcx+38h]
0x18003a5aa  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x18003a5b1  mov     edx, 82h
0x18003a5b6  mov     r9d, ebx
0x18003a5b9  call    WPP_SF_d
0x18003a5be  mov     rsi, [rsp+28h+arg_8]
0x18003a5c3  mov     eax, ebx
0x18003a5c5  mov     rbx, [rsp+28h+arg_0]
0x18003a5ca  add     rsp, 20h
0x18003a5ce  pop     rdi
0x18003a5cf  retn
```
