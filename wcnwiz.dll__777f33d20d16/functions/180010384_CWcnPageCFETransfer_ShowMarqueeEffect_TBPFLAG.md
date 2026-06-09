# CWcnPageCFETransfer::_ShowMarqueeEffect(TBPFLAG)

- ea: `0x180010384`
- end: `0x180010446`
- name: `?_ShowMarqueeEffect@CWcnPageCFETransfer@@AEAAXW4TBPFLAG@@@Z`
- size: `194`
- prototype: `void __fastcall(CWcnPageCFETransfer *__hidden this, enum TBPFLAG)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000fc40`
- `0x18000fd00`

## callees

- `0x18000d630`
- `0x180010384`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800103cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800103cc`
- `USER32!GetAncestor` at `0x1800103a5`
- `USER32!GetAncestor` at `0x1800103a5`

## pseudocode

```c
void __fastcall CWcnPageCFETransfer::_ShowMarqueeEffect(CWcnPageCFETransfer *this, unsigned int a2)
{
  HWND v2; // rcx
  HWND Ancestor; // rdi
  const char *Indent; // rax
  __int64 v6; // r10
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v2 = (HWND)*((_QWORD *)this + 42);
  ppv = 0;
  Ancestor = GetAncestor(v2, 2u);
  if ( CoCreateInstance(&CLSID_TaskbarList, 0, 1u, &GUID_ea1afb91_9e28_4b86_90e9_9e9f8a5eefaf, &ppv) >= 0 )
  {
    if ( (*(int (__fastcall **)(LPVOID, HWND, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, Ancestor, a2) < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      Indent = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 28, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, Indent);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
}

```

## disassembly

```asm
0x180010384  mov     [rsp+arg_8], rbx
0x180010389  push    rdi
0x18001038a  sub     rsp, 30h
0x18001038e  mov     rcx, [rcx+150h]; hwnd
0x180010395  mov     ebx, edx
0x180010397  mov     edx, 2; gaFlags
0x18001039c  mov     [rsp+38h+arg_0], 0
0x1800103a5  call    cs:__imp_GetAncestor
0x1800103ab  xor     edx, edx; pUnkOuter
0x1800103ad  lea     r9, _GUID_ea1afb91_9e28_4b86_90e9_9e9f8a5eefaf; riid
0x1800103b4  mov     rdi, rax
0x1800103b7  lea     rcx, CLSID_TaskbarList; rclsid
0x1800103be  lea     rax, [rsp+38h+arg_0]
0x1800103c3  mov     [rsp+38h+ppv], rax; ppv
0x1800103c8  lea     r8d, [rdx+1]; dwClsContext
0x1800103cc  call    cs:__imp_CoCreateInstance
0x1800103d2  test    eax, eax
0x1800103d4  js      short loc_18001043B
0x1800103d6  mov     rcx, [rsp+38h+arg_0]
0x1800103db  mov     r8d, ebx
0x1800103de  mov     rdx, [rcx]
0x1800103e1  mov     rax, [rdx+50h]
0x1800103e5  mov     rdx, rdi
0x1800103e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ed  test    eax, eax
0x1800103ef  jns     short loc_18001042A
0x1800103f1  mov     r10, cs:WPP_GLOBAL_Control
0x1800103f8  lea     rax, WPP_GLOBAL_Control
0x1800103ff  cmp     r10, rax
0x180010402  jz      short loc_18001042A
0x180010404  cmp     byte ptr [r10+19h], 4
0x180010409  jb      short loc_18001042A
0x18001040b  xor     ecx, ecx; int
0x18001040d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180010412  mov     rcx, [r10+10h]
0x180010416  lea     r8, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids
0x18001041d  mov     edx, 1Ch
0x180010422  mov     r9, rax
0x180010425  call    WPP_SF_s
0x18001042a  mov     rcx, [rsp+38h+arg_0]
0x18001042f  mov     rax, [rcx]
0x180010432  mov     rax, [rax+10h]
0x180010436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001043b  mov     rbx, [rsp+38h+arg_8]
0x180010440  add     rsp, 30h
0x180010444  pop     rdi
0x180010445  retn
```
