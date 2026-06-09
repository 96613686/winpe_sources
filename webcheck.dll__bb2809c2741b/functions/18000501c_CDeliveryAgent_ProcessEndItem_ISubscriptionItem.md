# CDeliveryAgent::ProcessEndItem(ISubscriptionItem *)

- ea: `0x18000501c`
- end: `0x1800051c0`
- name: `?ProcessEndItem@CDeliveryAgent@@AEAAJPEAUISubscriptionItem@@@Z`
- size: `420`
- prototype: `int(CDeliveryAgent *__hidden this, struct ISubscriptionItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800053a4`

## callees

- `0x18000501c`
- `0x18000c1d0`
- `0x1800106d0`
- `0x18001d944`
- `0x18001da30`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180005185`
- `KERNEL32!LocalFree` at `0x180005185`
- `ole32!PropVariantClear` at `0x180005155`
- `ole32!PropVariantClear` at `0x180005155`
- `ole32!CoCreateInstance` at `0x180005081`
- `ole32!CoCreateInstance` at `0x180005081`

## string_xrefs

- `0x180005043`: `DesktopComponent`

## pseudocode

```c
__int64 __fastcall CDeliveryAgent::ProcessEndItem(CDeliveryAgent *this, struct ISubscriptionItem *a2)
{
  int OLESTR; // eax
  unsigned int v5; // r9d
  unsigned __int16 *v6; // rdi
  unsigned int v7; // r9d
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+30h] BYREF

  if ( *((int *)this + 27) >= 0 )
  {
    LODWORD(ppv) = 0;
    if ( (int)ReadDWORD(a2, L"DesktopComponent", (unsigned int *)&ppv) >= 0 && (_DWORD)ppv == 1 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_ActiveDesktop, 0, 1u, &IID_IActiveDesktop, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 28);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  if ( *((int *)this + 27) >= 0 && *((_DWORD *)this + 27) != 1 )
  {
    LODWORD(ppv) = 0;
    if ( (int)ReadDWORD(a2, L"EnableShortcutGleam", (unsigned int *)&ppv) >= 0 && (_DWORD)ppv )
    {
      hMem = 0;
      OLESTR = ReadOLESTR(a2, L"URL", (unsigned __int16 **)&hMem);
      v6 = (unsigned __int16 *)hMem;
      if ( OLESTR >= 0 )
      {
        memset(&pvar, 0, sizeof(pvar));
        if ( (int)IntSiteHelper((const unsigned __int16 *)hMem, &stru_18002DC20, &pvar, v5, 0) >= 0 && pvar.vt == 19 )
        {
          pvar.lVal |= 1u;
        }
        else
        {
          PropVariantClear((PROPVARIANT *)&pvar);
          pvar.vt = 19;
          pvar.lVal = 1;
        }
        IntSiteHelper(v6, &stru_18002DC20, &pvar, v7, 1);
      }
      LocalFree(v6);
    }
    if ( (int)ReadDWORD(a2, L"EmailNotification", (unsigned int *)&ppv) >= 0 && (_DWORD)ppv )
      SendEmailFromItem(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000501c  mov     [rsp-18h+arg_8], rbx
0x180005021  push    rbp
0x180005022  push    rdi
0x180005023  push    r15
0x180005025  mov     rbp, rsp
0x180005028  sub     rsp, 50h
0x18000502c  cmp     dword ptr [rcx+6Ch], 0
0x180005030  mov     rbx, rdx
0x180005033  mov     rdi, rcx
0x180005036  jl      short loc_1800050B0
0x180005038  lea     r8, [rbp+arg_0]; unsigned int *
0x18000503c  mov     dword ptr [rbp+arg_0], 0
0x180005043  lea     rdx, ?c_szPropDesktopComponent@@3QBGB; "DesktopComponent"
0x18000504a  mov     rcx, rbx; struct ISubscriptionItem *
0x18000504d  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x180005052  test    eax, eax
0x180005054  js      short loc_1800050B0
0x180005056  cmp     dword ptr [rbp+arg_0], 1
0x18000505a  jnz     short loc_1800050B0
0x18000505c  xor     edx, edx; pUnkOuter
0x18000505e  mov     [rbp+arg_0], 0
0x180005066  lea     rax, [rbp+arg_0]
0x18000506a  lea     r9, IID_IActiveDesktop; riid
0x180005071  mov     [rsp+50h+ppv], rax; ppv
0x180005076  lea     rcx, CLSID_ActiveDesktop; rclsid
0x18000507d  lea     r8d, [rdx+1]; dwClsContext
0x180005081  call    cs:__imp_CoCreateInstance
0x180005087  test    eax, eax
0x180005089  js      short loc_1800050B0
0x18000508b  mov     rcx, [rbp+arg_0]
0x18000508f  mov     edx, 1Ch
0x180005094  mov     rax, [rcx]
0x180005097  mov     rax, [rax+18h]
0x18000509b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a0  mov     rcx, [rbp+arg_0]
0x1800050a4  mov     rax, [rcx]
0x1800050a7  mov     rax, [rax+10h]
0x1800050ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b0  test    dword ptr [rdi+6Ch], 80000000h
0x1800050b7  jnz     loc_1800051B0
0x1800050bd  cmp     dword ptr [rdi+6Ch], 1
0x1800050c1  jz      loc_1800051B0
0x1800050c7  lea     r8, [rbp+arg_0]; unsigned int *
0x1800050cb  mov     dword ptr [rbp+arg_0], 0
0x1800050d2  lea     rdx, ?c_szPropEnableShortcutGleam@@3QBGB; "EnableShortcutGleam"
0x1800050d9  mov     rcx, rbx; struct ISubscriptionItem *
0x1800050dc  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x1800050e1  test    eax, eax
0x1800050e3  js      loc_18000518B
0x1800050e9  cmp     dword ptr [rbp+arg_0], 0
0x1800050ed  jz      loc_18000518B
0x1800050f3  lea     r8, [rbp+hMem]; unsigned __int16 **
0x1800050f7  mov     [rbp+hMem], 0
0x1800050ff  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x180005106  mov     rcx, rbx; struct ISubscriptionItem *
0x180005109  call    ?ReadOLESTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z; ReadOLESTR(ISubscriptionItem *,ushort const *,ushort * *)
0x18000510e  mov     rdi, [rbp+hMem]
0x180005112  test    eax, eax
0x180005114  js      short loc_180005182
0x180005116  xor     eax, eax
0x180005118  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18000511c  xorps   xmm0, xmm0
0x18000511f  mov     [rbp+var_10], rax
0x180005123  lea     rdx, stru_18002DC20; struct tagPROPSPEC *
0x18000512a  mov     dword ptr [rsp+50h+ppv], eax; int
0x18000512e  mov     rcx, rdi; unsigned __int16 *
0x180005131  movups  xmmword ptr [rbp+pvar], xmm0
0x180005135  call    ?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z; IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)
0x18000513a  mov     r15d, 13h
0x180005140  test    eax, eax
0x180005142  js      short loc_180005151
0x180005144  cmp     r15w, word ptr [rbp+pvar]
0x180005149  jnz     short loc_180005151
0x18000514b  or      dword ptr [rbp+pvar+8], 1
0x18000514f  jmp     short loc_180005167
0x180005151  lea     rcx, [rbp+pvar]; pvar
0x180005155  call    cs:__imp_PropVariantClear
0x18000515b  mov     word ptr [rbp+pvar], r15w
0x180005160  mov     dword ptr [rbp+pvar+8], 1
0x180005167  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18000516b  mov     dword ptr [rsp+50h+ppv], 1; int
0x180005173  lea     rdx, stru_18002DC20; struct tagPROPSPEC *
0x18000517a  mov     rcx, rdi; unsigned __int16 *
0x18000517d  call    ?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z; IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)
0x180005182  mov     rcx, rdi; hMem
0x180005185  call    cs:__imp_LocalFree
0x18000518b  lea     r8, [rbp+arg_0]; unsigned int *
0x18000518f  mov     rcx, rbx; struct ISubscriptionItem *
0x180005192  lea     rdx, ?c_szPropEmailNotf@@3QBGB; "EmailNotification"
0x180005199  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000519e  test    eax, eax
0x1800051a0  js      short loc_1800051B0
0x1800051a2  cmp     dword ptr [rbp+arg_0], 0
0x1800051a6  jz      short loc_1800051B0
0x1800051a8  mov     rcx, rbx; struct ISubscriptionItem *
0x1800051ab  call    ?SendEmailFromItem@@YAJPEAUISubscriptionItem@@@Z; SendEmailFromItem(ISubscriptionItem *)
0x1800051b0  mov     rbx, [rsp+50h+arg_8]
0x1800051b5  xor     eax, eax
0x1800051b7  add     rsp, 50h
0x1800051bb  pop     r15
0x1800051bd  pop     rdi
0x1800051be  pop     rbp
0x1800051bf  retn
```
