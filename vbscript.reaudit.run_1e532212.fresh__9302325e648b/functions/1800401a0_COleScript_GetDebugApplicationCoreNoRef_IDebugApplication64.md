# COleScript::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)

- ea: `0x1800401a0`
- end: `0x18004033f`
- name: `?GetDebugApplicationCoreNoRef@COleScript@@IEAAJPEAPEAUIDebugApplication64@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IDebugApplication64 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180020398`
- `0x18005c120`

## callees

- `0x18003a2e4`
- `0x18003a3c4`
- `0x18003f9e4`
- `0x1800401a0`
- `0x180077010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800402da`
- `OLE32!CoCreateInstance` at `0x1800402da`

## pseudocode

```c
__int64 __fastcall COleScript::GetDebugApplicationCoreNoRef(COleScript *this, struct IDebugApplication64 **a2)
{
  bool v2; // zf
  struct IDebugApplication64 **v5; // rsi
  HRESULT Instance; // edi
  bool v7; // sf
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct IActiveScriptSiteDebug64 *ppv; // [rsp+60h] [rbp+8h] BYREF

  v2 = (*((_BYTE *)this + 800) & 2) == 0;
  ppv = 0;
  if ( v2 && (int)COleScript::GetDebugSiteCoreNoRef(this, &ppv) >= 0 )
  {
    v5 = (struct IDebugApplication64 **)((char *)this + 744);
    Instance = ((__int64 (__fastcall *)(struct IActiveScriptSiteDebug64 *, char *))ppv->lpVtbl->GetApplication)(
                 ppv,
                 (char *)this + 744);
    v7 = Instance < 0;
  }
  else
  {
    ppv = 0;
    if ( !(unsigned int)FUserWantsDebugger() )
    {
      Instance = -2147467259;
      goto LABEL_6;
    }
    Instance = CoCreateInstance(&CLSID_ProcessDebugManager, 0, 0x17u, &IID_IProcessDebugManager64, (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_6;
    v5 = (struct IDebugApplication64 **)((char *)this + 744);
    Instance = ((__int64 (__fastcall *)(struct IActiveScriptSiteDebug64 *, char *))ppv->lpVtbl->GetApplication)(
                 ppv,
                 (char *)this + 744);
    ((void (__fastcall *)(struct IActiveScriptSiteDebug64 *))ppv->lpVtbl->Release)(ppv);
    v7 = Instance < 0;
  }
  if ( !v7 )
  {
    Instance = COleScript::SetupNewDebugApplication(this);
    if ( Instance >= 0 )
    {
      *a2 = *v5;
      return 0;
    }
  }
LABEL_6:
  *((_DWORD *)this + 200) |= 1u;
  if ( *((_QWORD *)this + 93) )
  {
    v8 = *((_QWORD *)this + 94);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 94) = 0;
    }
    v9 = *((_QWORD *)this + 95);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 95) = 0;
    }
    v10 = *((_QWORD *)this + 96);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 96) = 0;
    }
    v11 = *((_QWORD *)this + 93);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *((_QWORD *)this + 93) = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800401a0  push    rbx
0x1800401a2  push    rsi
0x1800401a3  push    rdi
0x1800401a4  push    r14
0x1800401a6  sub     rsp, 38h
0x1800401aa  test    byte ptr [rcx+320h], 2
0x1800401b1  mov     r14, rdx
0x1800401b4  mov     rbx, rcx
0x1800401b7  mov     [rsp+58h+arg_0], 0
0x1800401c0  jnz     short loc_1800401F4
0x1800401c2  lea     rdx, [rsp+58h+arg_0]; struct IActiveScriptSiteDebug64 **
0x1800401c7  call    ?GetDebugSiteCoreNoRef@COleScript@@IEAAJPEAPEAUIActiveScriptSiteDebug64@@@Z; COleScript::GetDebugSiteCoreNoRef(IActiveScriptSiteDebug64 * *)
0x1800401cc  test    eax, eax
0x1800401ce  js      short loc_1800401F4
0x1800401d0  mov     rcx, [rsp+58h+arg_0]
0x1800401d5  lea     rsi, [rbx+2E8h]
0x1800401dc  mov     rdx, rsi
0x1800401df  mov     rax, [rcx]
0x1800401e2  mov     rax, [rax+20h]
0x1800401e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401eb  mov     edi, eax
0x1800401ed  test    eax, eax
0x1800401ef  jmp     loc_18004031A
0x1800401f4  mov     [rsp+58h+arg_0], 0
0x1800401fd  call    FUserWantsDebugger
0x180040202  test    eax, eax
0x180040204  jnz     loc_1800402BC
0x18004020a  mov     edi, 80004005h
0x18004020f  or      dword ptr [rbx+320h], 1
0x180040216  cmp     qword ptr [rbx+2E8h], 0
0x18004021e  jz      loc_1800402B0
0x180040224  mov     rcx, [rbx+2F0h]
0x18004022b  test    rcx, rcx
0x18004022e  jz      short loc_180040247
0x180040230  mov     rax, [rcx]
0x180040233  mov     rax, [rax+10h]
0x180040237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004023c  mov     qword ptr [rbx+2F0h], 0
0x180040247  mov     rcx, [rbx+2F8h]
0x18004024e  test    rcx, rcx
0x180040251  jz      short loc_18004026A
0x180040253  mov     rax, [rcx]
0x180040256  mov     rax, [rax+10h]
0x18004025a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004025f  mov     qword ptr [rbx+2F8h], 0
0x18004026a  mov     rcx, [rbx+300h]
0x180040271  test    rcx, rcx
0x180040274  jz      short loc_18004028D
0x180040276  mov     rax, [rcx]
0x180040279  mov     rax, [rax+10h]
0x18004027d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040282  mov     qword ptr [rbx+300h], 0
0x18004028d  mov     rcx, [rbx+2E8h]
0x180040294  test    rcx, rcx
0x180040297  jz      short loc_1800402B0
0x180040299  mov     rax, [rcx]
0x18004029c  mov     rax, [rax+10h]
0x1800402a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402a5  mov     qword ptr [rbx+2E8h], 0
0x1800402b0  mov     eax, edi
0x1800402b2  add     rsp, 38h
0x1800402b6  pop     r14
0x1800402b8  pop     rdi
0x1800402b9  pop     rsi
0x1800402ba  pop     rbx
0x1800402bb  retn
0x1800402bc  xor     edx, edx; pUnkOuter
0x1800402be  lea     rax, [rsp+58h+arg_0]
0x1800402c3  lea     r9, IID_IProcessDebugManager64; riid
0x1800402ca  mov     [rsp+58h+ppv], rax; ppv
0x1800402cf  lea     rcx, CLSID_ProcessDebugManager; rclsid
0x1800402d6  lea     r8d, [rdx+17h]; dwClsContext
0x1800402da  call    cs:__imp_CoCreateInstance
0x1800402e0  mov     edi, eax
0x1800402e2  test    eax, eax
0x1800402e4  js      loc_18004020F
0x1800402ea  mov     rcx, [rsp+58h+arg_0]
0x1800402ef  lea     rsi, [rbx+2E8h]
0x1800402f6  mov     rdx, rsi
0x1800402f9  mov     rax, [rcx]
0x1800402fc  mov     rax, [rax+20h]
0x180040300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040305  mov     rcx, [rsp+58h+arg_0]
0x18004030a  mov     edi, eax
0x18004030c  mov     rax, [rcx]
0x18004030f  mov     rax, [rax+10h]
0x180040313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040318  test    edi, edi
0x18004031a  js      loc_18004020F
0x180040320  mov     rcx, rbx; this
0x180040323  call    ?SetupNewDebugApplication@COleScript@@IEAAJXZ; COleScript::SetupNewDebugApplication(void)
0x180040328  mov     edi, eax
0x18004032a  test    eax, eax
0x18004032c  js      loc_18004020F
0x180040332  mov     rax, [rsi]
0x180040335  mov     [r14], rax
0x180040338  xor     eax, eax
0x18004033a  jmp     loc_1800402B2
```
