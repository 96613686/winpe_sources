# CScriptedDiagNativeHost::Initialize(ushort *,IScriptedDiagnosticInteraction *,ushort *,ushort *)

- ea: `0x1400028e0`
- end: `0x1400029eb`
- name: `?Initialize@CScriptedDiagNativeHost@@UEAAJPEAGPEAUIScriptedDiagnosticInteraction@@00@Z`
- size: `267`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned __int16 *, struct IScriptedDiagnosticInteraction *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140005964`
- `0x140007770`
- `0x140008010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140002982`
- `ole32!CoCreateInstance` at `0x140002982`

## pseudocode

```c
__int64 __fastcall CScriptedDiagNativeHost::Initialize(
        LPVOID *this,
        unsigned __int16 *a2,
        struct IScriptedDiagnosticInteraction *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v8; // r9d
  int v9; // r8d
  unsigned int v10; // ebx
  _QWORD *v11; // r14
  HRESULT v12; // eax
  IID rclsid; // [rsp+30h] [rbp-20h] BYREF

  rclsid.Data1 = 661635009;
  *(_DWORD *)&rclsid.Data2 = 1176098591;
  *(_DWORD *)rclsid.Data4 = -2130591321;
  *(_DWORD *)&rclsid.Data4[4] = -2082308601;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 104;
    v10 = -2147024809;
LABEL_12:
    SdpDebugTrace((unsigned int)this, L"CScriptedDiagNativeHost::Initialize", v9, v8);
    return v10;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    v9 = 105;
    v10 = -2147024809;
    goto LABEL_12;
  }
  if ( !a5 )
  {
    v8 = -2147024809;
    v9 = 106;
    v10 = -2147024809;
    goto LABEL_12;
  }
  v11 = this + 2;
  v12 = CoCreateInstance(&rclsid, 0, 0x15u, &IID_IScriptedDiagnosticHost, this + 2);
  v10 = v12;
  if ( v12 < 0 )
  {
    v9 = 113;
LABEL_11:
    v8 = v12;
    goto LABEL_12;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, struct IScriptedDiagnosticInteraction *, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)*v11 + 24LL))(
          *v11,
          a2,
          a3,
          a4,
          a5);
  v10 = v12;
  if ( v12 < 0 )
  {
    v9 = 119;
    goto LABEL_11;
  }
  return v10;
}

```

## disassembly

```asm
0x1400028e0  push    rbp
0x1400028e2  push    rbx
0x1400028e3  push    rsi
0x1400028e4  push    rdi
0x1400028e5  push    r12
0x1400028e7  push    r14
0x1400028e9  push    r15
0x1400028eb  mov     rbp, rsp
0x1400028ee  sub     rsp, 50h
0x1400028f2  mov     rax, cs:__security_cookie
0x1400028f9  xor     rax, rsp
0x1400028fc  mov     [rbp+var_10], rax
0x140002900  mov     rsi, [rbp+arg_20]
0x140002904  mov     r12, r9
0x140002907  mov     [rbp+rclsid.Data1], 276FBFC1h
0x14000290e  mov     rdi, r8
0x140002911  mov     dword ptr [rbp+rclsid.Data2], 4619D71Fh
0x140002918  mov     r15, rdx
0x14000291b  mov     dword ptr [rbp+rclsid.Data4], 8101C1A7h
0x140002922  mov     dword ptr [rbp+rclsid.Data4+4], 83E27E07h
0x140002929  test    rdx, rdx
0x14000292c  jnz     short loc_140002940
0x14000292e  mov     r9d, 80070057h
0x140002934  lea     r8d, [rdx+68h]
0x140002938  mov     ebx, r9d
0x14000293b  jmp     loc_1400029C2
0x140002940  test    rdi, rdi
0x140002943  jnz     short loc_140002954
0x140002945  mov     r9d, 80070057h
0x14000294b  lea     r8d, [rdi+69h]
0x14000294f  mov     ebx, r9d
0x140002952  jmp     short loc_1400029C2
0x140002954  test    rsi, rsi
0x140002957  jnz     short loc_140002968
0x140002959  mov     r9d, 80070057h
0x14000295f  lea     r8d, [rsi+6Ah]
0x140002963  mov     ebx, r9d
0x140002966  jmp     short loc_1400029C2
0x140002968  lea     r14, [rcx+10h]
0x14000296c  xor     edx, edx; pUnkOuter
0x14000296e  lea     r9, IID_IScriptedDiagnosticHost; riid
0x140002975  mov     [rsp+50h+ppv], r14; ppv
0x14000297a  lea     rcx, [rbp+rclsid]; rclsid
0x14000297e  lea     r8d, [rdx+15h]; dwClsContext
0x140002982  call    cs:__imp_CoCreateInstance
0x140002988  mov     ebx, eax
0x14000298a  test    eax, eax
0x14000298c  jns     short loc_140002996
0x14000298e  mov     r8d, 71h ; 'q'
0x140002994  jmp     short loc_1400029BF
0x140002996  mov     rcx, [r14]
0x140002999  mov     r9, r12
0x14000299c  mov     r8, rdi
0x14000299f  mov     [rsp+50h+ppv], rsi
0x1400029a4  mov     rdx, r15
0x1400029a7  mov     rax, [rcx]
0x1400029aa  mov     rax, [rax+18h]
0x1400029ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029b3  mov     ebx, eax
0x1400029b5  test    eax, eax
0x1400029b7  jns     short loc_1400029CE
0x1400029b9  mov     r8d, 77h ; 'w'; int
0x1400029bf  mov     r9d, eax; int
0x1400029c2  lea     rdx, aCscripteddiagn_3; "CScriptedDiagNativeHost::Initialize"
0x1400029c9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400029ce  mov     eax, ebx
0x1400029d0  mov     rcx, [rbp+var_10]
0x1400029d4  xor     rcx, rsp; StackCookie
0x1400029d7  call    __security_check_cookie
0x1400029dc  add     rsp, 50h
0x1400029e0  pop     r15
0x1400029e2  pop     r14
0x1400029e4  pop     r12
0x1400029e6  pop     rdi
0x1400029e7  pop     rsi
0x1400029e8  pop     rbx
0x1400029e9  pop     rbp
0x1400029ea  retn
```
