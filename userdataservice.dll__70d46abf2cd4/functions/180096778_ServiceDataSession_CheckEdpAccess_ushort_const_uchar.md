# ServiceDataSession::CheckEdpAccess(ushort const *,uchar *)

- ea: `0x180096778`
- end: `0x18009691b`
- name: `?CheckEdpAccess@ServiceDataSession@@QEAAJPEBGPEAE@Z`
- size: `419`
- prototype: `int(ServiceDataSession *__hidden this, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180009a90`

## callees

- `0x180008f0c`
- `0x180096778`
- `0x180096924`
- `0x180096944`
- `0x1800986b0`
- `0x18012c776`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800967e0`
- `ntdll!RtlNtStatusToDosError` at `0x1800967e0`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x1800968c0`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x1800968c0`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x180096870`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x180096870`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180096844`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180096844`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x18009689b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x18009689b`

## string_xrefs

- `0x1800967ff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800968d2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall ServiceDataSession::CheckEdpAccess(ServiceDataSession *this, const unsigned __int16 *a2, bool *a3)
{
  NTSTATUS EdpEnforcementLevel2; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rax
  int ContextForBinaryPath; // eax
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  *a3 = 1;
  if ( (unsigned __int8)IsEdpGetContextForPackageFullNamePresent()
    && (unsigned __int8)IsEdpGetContextForPackageFullNamePresent()
    && wcscmp_0(a2, L"{E2CAA6FC-5124-48F5-806B-8E64ABCDEBA1}") )
  {
    v14 = 0;
    EdpEnforcementLevel2 = EdpGetEdpEnforcementLevel2(&v14);
    v7 = RtlNtStatusToDosError(EdpEnforcementLevel2);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      Log_HREvent(
        v8,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        1573);
      return v8;
    }
    if ( v14 )
    {
      v10 = *((_QWORD *)this + 227);
      v15 = 0;
      if ( *((_QWORD *)this + 226) == v10 )
      {
        v13 = *((_QWORD *)this + 236);
        if ( v13 == *((_QWORD *)this + 237) )
          goto LABEL_24;
        ContextForBinaryPath = EdpGetContextForBinaryPath(v13, &v15);
        v8 = ContextForBinaryPath;
        if ( ContextForBinaryPath < 0 )
        {
          v12 = 1586;
          goto LABEL_22;
        }
      }
      else
      {
        ContextForBinaryPath = EdpGetContextForPackageFullName(*((_QWORD *)this + 230), &v15);
        v8 = ContextForBinaryPath;
        if ( ContextForBinaryPath < 0 )
        {
          v12 = 1582;
LABEL_22:
          Log_HREvent(
            (unsigned int)ContextForBinaryPath,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            v12);
          wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v15);
          return v8;
        }
      }
      if ( v15 )
      {
        v14 = 0;
        ContextForBinaryPath = EdpIsContextExemptOrEnlightenedAllowed(a2, v15, &v14);
        v8 = ContextForBinaryPath;
        if ( ContextForBinaryPath < 0 )
        {
          v12 = 1592;
          goto LABEL_22;
        }
        if ( v14 != 1 )
        {
          ContextForBinaryPath = EdpCheckAccessForContext(a2, v15, &v14);
          v8 = ContextForBinaryPath;
          if ( ContextForBinaryPath < 0 )
          {
            v12 = 1596;
            goto LABEL_22;
          }
          *a3 = v14 == 1;
        }
        goto LABEL_25;
      }
LABEL_24:
      *a3 = 0;
LABEL_25:
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180096778  mov     [rsp-28h+arg_0], rbx
0x18009677d  push    rbp
0x18009677e  push    rsi
0x18009677f  push    rdi
0x180096780  push    r12
0x180096782  push    r14
0x180096784  mov     rbp, rsp
0x180096787  sub     rsp, 30h
0x18009678b  mov     r12d, 1
0x180096791  mov     rsi, r8
0x180096794  mov     [r8], r12b
0x180096797  mov     r14, rdx
0x18009679a  mov     rdi, rcx
0x18009679d  call    IsEdpGetContextForPackageFullNamePresent
0x1800967a2  test    al, al
0x1800967a4  jz      loc_180096908
0x1800967aa  call    IsEdpGetContextForPackageFullNamePresent
0x1800967af  test    al, al
0x1800967b1  jz      loc_180096908
0x1800967b7  lea     rdx, aE2caa6fc512448; "{E2CAA6FC-5124-48F5-806B-8E64ABCDEBA1}"
0x1800967be  mov     rcx, r14; String1
0x1800967c1  call    wcscmp_0
0x1800967c6  test    eax, eax
0x1800967c8  jz      loc_180096908
0x1800967ce  lea     rcx, [rbp+arg_10]
0x1800967d2  mov     [rbp+arg_10], 0
0x1800967d9  call    EdpGetEdpEnforcementLevel2
0x1800967de  mov     ecx, eax; Status
0x1800967e0  call    cs:__imp_RtlNtStatusToDosError
0x1800967e6  mov     ebx, eax
0x1800967e8  test    eax, eax
0x1800967ea  jle     short loc_1800967F5
0x1800967ec  movzx   ebx, ax
0x1800967ef  or      ebx, 80070000h
0x1800967f5  test    ebx, ebx
0x1800967f7  jns     short loc_180096817
0x1800967f9  mov     r9d, 625h
0x1800967ff  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180096806  mov     edx, r12d
0x180096809  mov     ecx, ebx
0x18009680b  call    Log_HREvent
0x180096810  mov     eax, ebx
0x180096812  jmp     loc_18009690A
0x180096817  cmp     [rbp+arg_10], 0
0x18009681b  jz      loc_180096908
0x180096821  mov     rax, [rdi+718h]
0x180096828  mov     [rbp+arg_18], 0
0x180096830  cmp     [rdi+710h], rax
0x180096837  jz      short loc_180096858
0x180096839  mov     rcx, [rdi+730h]
0x180096840  lea     rdx, [rbp+arg_18]
0x180096844  call    cs:__imp_EdpGetContextForPackageFullName
0x18009684a  mov     ebx, eax
0x18009684c  test    eax, eax
0x18009684e  jns     short loc_180096884
0x180096850  mov     r9d, 62Eh
0x180096856  jmp     short loc_1800968D2
0x180096858  mov     rcx, [rdi+760h]
0x18009685f  cmp     rcx, [rdi+768h]
0x180096866  jz      loc_1800968FC
0x18009686c  lea     rdx, [rbp+arg_18]
0x180096870  call    cs:__imp_EdpGetContextForBinaryPath
0x180096876  mov     ebx, eax
0x180096878  test    eax, eax
0x18009687a  jns     short loc_180096884
0x18009687c  mov     r9d, 632h
0x180096882  jmp     short loc_1800968D2
0x180096884  mov     rdx, [rbp+arg_18]
0x180096888  test    rdx, rdx
0x18009688b  jz      short loc_1800968FC
0x18009688d  lea     r8, [rbp+arg_10]
0x180096891  mov     [rbp+arg_10], 0
0x180096898  mov     rcx, r14
0x18009689b  call    cs:__imp_EdpIsContextExemptOrEnlightenedAllowed
0x1800968a1  mov     ebx, eax
0x1800968a3  test    eax, eax
0x1800968a5  jns     short loc_1800968AF
0x1800968a7  mov     r9d, 638h
0x1800968ad  jmp     short loc_1800968D2
0x1800968af  cmp     [rbp+arg_10], r12d
0x1800968b3  jz      short loc_1800968FF
0x1800968b5  mov     rdx, [rbp+arg_18]
0x1800968b9  lea     r8, [rbp+arg_10]
0x1800968bd  mov     rcx, r14
0x1800968c0  call    cs:__imp_EdpCheckAccessForContext
0x1800968c6  mov     ebx, eax
0x1800968c8  test    eax, eax
0x1800968ca  jns     short loc_1800968F1
0x1800968cc  mov     r9d, 63Ch
0x1800968d2  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800968d9  mov     edx, r12d
0x1800968dc  mov     ecx, eax
0x1800968de  call    Log_HREvent
0x1800968e3  lea     rcx, [rbp+arg_18]
0x1800968e7  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x1800968ec  jmp     loc_180096810
0x1800968f1  cmp     [rbp+arg_10], r12d
0x1800968f5  setz    al
0x1800968f8  mov     [rsi], al
0x1800968fa  jmp     short loc_1800968FF
0x1800968fc  mov     byte ptr [rsi], 0
0x1800968ff  lea     rcx, [rbp+arg_18]
0x180096903  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180096908  xor     eax, eax
0x18009690a  mov     rbx, [rsp+30h+arg_0]
0x18009690f  add     rsp, 30h
0x180096913  pop     r14
0x180096915  pop     r12
0x180096917  pop     rdi
0x180096918  pop     rsi
0x180096919  pop     rbp
0x18009691a  retn
```
