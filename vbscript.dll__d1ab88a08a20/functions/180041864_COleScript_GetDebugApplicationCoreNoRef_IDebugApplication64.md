# COleScript::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)

- ea: `0x180041864`
- end: `0x180041a0a`
- name: `?GetDebugApplicationCoreNoRef@COleScript@@IEAAJPEAPEAUIDebugApplication64@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IDebugApplication64 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001b588`
- `0x18005dca0`

## callees

- `0x18003bc24`
- `0x18003bdd4`
- `0x180041070`
- `0x180041864`
- `0x18007a010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x18004199f`
- `OLE32!CoCreateInstance` at `0x18004199f`

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
0x180041864  push    rbx
0x180041866  push    rsi
0x180041867  push    rdi
0x180041868  push    r14
0x18004186a  sub     rsp, 38h
0x18004186e  test    byte ptr [rcx+320h], 2
0x180041875  mov     r14, rdx
0x180041878  mov     rbx, rcx
0x18004187b  mov     [rsp+58h+arg_0], 0
0x180041884  jnz     short loc_1800418B8
0x180041886  lea     rdx, [rsp+58h+arg_0]; struct IActiveScriptSiteDebug64 **
0x18004188b  call    ?GetDebugSiteCoreNoRef@COleScript@@IEAAJPEAPEAUIActiveScriptSiteDebug64@@@Z; COleScript::GetDebugSiteCoreNoRef(IActiveScriptSiteDebug64 * *)
0x180041890  test    eax, eax
0x180041892  js      short loc_1800418B8
0x180041894  mov     rcx, [rsp+58h+arg_0]
0x180041899  lea     rsi, [rbx+2E8h]
0x1800418a0  mov     rdx, rsi
0x1800418a3  mov     rax, [rcx]
0x1800418a6  mov     rax, [rax+20h]
0x1800418aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418af  mov     edi, eax
0x1800418b1  test    eax, eax
0x1800418b3  jmp     loc_1800419E5
0x1800418b8  mov     [rsp+58h+arg_0], 0
0x1800418c1  call    FUserWantsDebugger
0x1800418c6  test    eax, eax
0x1800418c8  jnz     loc_180041981
0x1800418ce  mov     edi, 80004005h
0x1800418d3  or      dword ptr [rbx+320h], 1
0x1800418da  cmp     qword ptr [rbx+2E8h], 0
0x1800418e2  jz      loc_180041974
0x1800418e8  mov     rcx, [rbx+2F0h]
0x1800418ef  test    rcx, rcx
0x1800418f2  jz      short loc_18004190B
0x1800418f4  mov     rax, [rcx]
0x1800418f7  mov     rax, [rax+10h]
0x1800418fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041900  mov     qword ptr [rbx+2F0h], 0
0x18004190b  mov     rcx, [rbx+2F8h]
0x180041912  test    rcx, rcx
0x180041915  jz      short loc_18004192E
0x180041917  mov     rax, [rcx]
0x18004191a  mov     rax, [rax+10h]
0x18004191e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041923  mov     qword ptr [rbx+2F8h], 0
0x18004192e  mov     rcx, [rbx+300h]
0x180041935  test    rcx, rcx
0x180041938  jz      short loc_180041951
0x18004193a  mov     rax, [rcx]
0x18004193d  mov     rax, [rax+10h]
0x180041941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041946  mov     qword ptr [rbx+300h], 0
0x180041951  mov     rcx, [rbx+2E8h]
0x180041958  test    rcx, rcx
0x18004195b  jz      short loc_180041974
0x18004195d  mov     rax, [rcx]
0x180041960  mov     rax, [rax+10h]
0x180041964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041969  mov     qword ptr [rbx+2E8h], 0
0x180041974  mov     eax, edi
0x180041976  add     rsp, 38h
0x18004197a  pop     r14
0x18004197c  pop     rdi
0x18004197d  pop     rsi
0x18004197e  pop     rbx
0x18004197f  retn
0x180041981  xor     edx, edx; pUnkOuter
0x180041983  lea     rax, [rsp+58h+arg_0]
0x180041988  lea     r9, IID_IProcessDebugManager64; riid
0x18004198f  mov     [rsp+58h+ppv], rax; ppv
0x180041994  lea     rcx, CLSID_ProcessDebugManager; rclsid
0x18004199b  lea     r8d, [rdx+17h]; dwClsContext
0x18004199f  call    cs:__imp_CoCreateInstance
0x1800419a6  nop     dword ptr [rax+rax+00h]
0x1800419ab  mov     edi, eax
0x1800419ad  test    eax, eax
0x1800419af  js      loc_1800418D3
0x1800419b5  mov     rcx, [rsp+58h+arg_0]
0x1800419ba  lea     rsi, [rbx+2E8h]
0x1800419c1  mov     rdx, rsi
0x1800419c4  mov     rax, [rcx]
0x1800419c7  mov     rax, [rax+20h]
0x1800419cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419d0  mov     rcx, [rsp+58h+arg_0]
0x1800419d5  mov     edi, eax
0x1800419d7  mov     rax, [rcx]
0x1800419da  mov     rax, [rax+10h]
0x1800419de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419e3  test    edi, edi
0x1800419e5  js      loc_1800418D3
0x1800419eb  mov     rcx, rbx; this
0x1800419ee  call    ?SetupNewDebugApplication@COleScript@@IEAAJXZ; COleScript::SetupNewDebugApplication(void)
0x1800419f3  mov     edi, eax
0x1800419f5  test    eax, eax
0x1800419f7  js      loc_1800418D3
0x1800419fd  mov     rax, [rsi]
0x180041a00  mov     [r14], rax
0x180041a03  xor     eax, eax
0x180041a05  jmp     loc_180041976
```
