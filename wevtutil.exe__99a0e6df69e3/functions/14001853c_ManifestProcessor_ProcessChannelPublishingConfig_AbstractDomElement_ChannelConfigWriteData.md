# ManifestProcessor::ProcessChannelPublishingConfig(AbstractDomElement &,ChannelConfigWriteData &)

- ea: `0x14001853c`
- end: `0x140018cd2`
- name: `?ProcessChannelPublishingConfig@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEAVChannelConfigWriteData@@@Z`
- size: `1942`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, struct AbstractDomElement *, struct ChannelConfigWriteData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400178bc`

## callees

- `0x140008170`
- `0x14001853c`
- `0x140019a68`
- `0x140021b00`
- `0x140022cec`
- `0x14002b108`
- `0x14002b1ec`
- `0x14002f6c8`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018613`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001863c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001868a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400186b8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018755`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018782`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400187c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400187f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018837`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018864`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018919`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018946`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018613`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001863c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001868a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400186b8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018755`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018782`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400187c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400187f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018837`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018864`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018919`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018946`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1400186a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1400186a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140018626`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14001876c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1400187dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14001884e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1400188bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140018930`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140018626`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14001876c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1400187dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x14001884e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1400188bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140018930`

## string_xrefs

- `0x14001898e`: `sidType`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ManifestProcessor::ProcessChannelPublishingConfig(
        ManifestProcessor *this,
        struct AbstractDomElement *a2,
        struct ChannelConfigWriteData *a3)
{
  __int64 *v4; // rbx
  __int64 v5; // r14
  const wchar_t *v6; // rsi
  wchar_t *v7; // rbx
  unsigned int v8; // ebx
  const char *v9; // r8
  __int64 v10; // rbx
  const char *v11; // r8
  const char *v12; // r8
  unsigned int v13; // ebx
  const char *v14; // r8
  unsigned int v15; // ebx
  const char *v16; // r8
  unsigned int v17; // ebx
  const char *v18; // r8
  unsigned int v19; // ebx
  const char *v20; // r8
  unsigned int v21; // ebx
  const char *v22; // r8
  wchar_t *EndPtr; // [rsp+20h] [rbp-59h] BYREF
  __int64 v24; // [rsp+28h] [rbp-51h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-49h] BYREF
  _WORD *v26; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *v27; // [rsp+60h] [rbp-19h] BYREF
  wchar_t *v28; // [rsp+68h] [rbp-11h] BYREF
  wchar_t *v29; // [rsp+70h] [rbp-9h] BYREF
  wchar_t *v30; // [rsp+78h] [rbp-1h] BYREF
  wchar_t *v31; // [rsp+80h] [rbp+7h] BYREF
  __int64 v32; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v33[8]; // [rsp+90h] [rbp+17h] BYREF
  __int128 v34; // [rsp+98h] [rbp+1Fh] BYREF

  (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v32);
  v24 = 0;
  while ( 1 )
  {
    v4 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v32 + 8LL))(v32, v33);
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v24);
    v24 = *v4;
    v5 = v24;
    *v4 = 0;
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(v33);
    if ( !v5 )
      break;
    v6 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v7 = (wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    EndPtr = v7;
    if ( !wcscmp_0(v6, L"level") )
    {
      if ( v7 && *v7 )
      {
        EndPtr = 0;
        *(_DWORD *)_o__errno() = 0;
        v8 = wcstoul(v7, &EndPtr, 0);
        if ( *EndPtr || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v9, 341);
          throw (EvtException *)pExceptionObject;
        }
        if ( v8 > 0xFF )
          LOBYTE(v8) = -1;
        *((_BYTE *)a3 + 114) = v8;
        *((_BYTE *)a3 + 242) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"keywords") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v26 = 0;
        v10 = _o__wcstoui64(v7, &v26, 0);
        if ( *v26 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v11, 357);
          throw (EvtException *)pExceptionObject;
        }
        *((_QWORD *)a3 + 8) = v10;
        *((_BYTE *)a3 + 243) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"controlGuid") )
    {
      if ( v7 && *v7 )
      {
        v34 = 0;
        if ( !tlx::string_to_guid<wchar_t const *>(&v34, &EndPtr) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v12, 370);
          throw (EvtException *)pExceptionObject;
        }
        *(_OWORD *)((char *)a3 + 72) = v34;
        *((_BYTE *)a3 + 244) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"bufferSize") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v27 = 0;
        v13 = wcstoul(v7, &v27, 0);
        if ( *v27 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v14, 386);
          throw (EvtException *)pExceptionObject;
        }
        *((_DWORD *)a3 + 22) = v13;
        *((_BYTE *)a3 + 245) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"fileMax") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v28 = 0;
        v15 = wcstoul(v7, &v28, 0);
        if ( *v28 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v16, 402);
          throw (EvtException *)pExceptionObject;
        }
        *((_DWORD *)a3 + 26) = v15;
        *((_BYTE *)a3 + 252) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"minBuffers") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v29 = 0;
        v17 = wcstoul(v7, &v29, 0);
        if ( *v29 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v18, 418);
          throw (EvtException *)pExceptionObject;
        }
        *((_DWORD *)a3 + 23) = v17;
        *((_BYTE *)a3 + 246) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"maxBuffers") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v30 = 0;
        v19 = wcstoul(v7, &v30, 0);
        if ( *v30 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v20, 434);
          throw (EvtException *)pExceptionObject;
        }
        *((_DWORD *)a3 + 24) = v19;
        *((_BYTE *)a3 + 247) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"latency") )
    {
      if ( v7 && *v7 )
      {
        *(_DWORD *)_o__errno() = 0;
        v31 = 0;
        v21 = wcstoul(v7, &v31, 0);
        if ( *v31 || *(_DWORD *)_o__errno() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v22, 450);
          throw (EvtException *)pExceptionObject;
        }
        *((_DWORD *)a3 + 25) = v21;
        *((_BYTE *)a3 + 248) |= 1u;
      }
    }
    else if ( !wcscmp_0(v6, L"clockType") )
    {
      *((_BYTE *)a3 + 112) = ParseChannelClockType(v7);
      *((_BYTE *)a3 + 249) |= 1u;
    }
    else if ( !wcscmp_0(v6, L"sidType") )
    {
      *((_BYTE *)a3 + 113) = ParseChannelSidType(v7);
      *((_BYTE *)a3 + 250) |= 1u;
    }
  }
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v24);
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v32);
}

```

## disassembly

```asm
0x14001853c  mov     [rsp-8+arg_0], rbx
0x140018541  push    rbp
0x140018542  push    rsi
0x140018543  push    rdi
0x140018544  push    r14
0x140018546  push    r15
0x140018548  lea     rbp, [rsp-37h]
0x14001854d  sub     rsp, 0B0h
0x140018554  mov     rax, cs:__security_cookie
0x14001855b  xor     rax, rsp
0x14001855e  mov     [rbp+57h+var_28], rax
0x140018562  mov     rdi, r8
0x140018565  mov     rcx, rdx
0x140018568  mov     rax, [rdx]
0x14001856b  lea     rdx, [rbp+57h+var_48]
0x14001856f  mov     rax, [rax+18h]
0x140018573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018578  nop
0x140018579  xor     r15d, r15d
0x14001857c  mov     [rbp+57h+var_A8], r15
0x140018580  mov     rcx, [rbp+57h+var_48]
0x140018584  mov     rax, [rcx]
0x140018587  lea     rdx, [rbp+57h+var_40]
0x14001858b  mov     rax, [rax+8]
0x14001858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018594  mov     rbx, rax
0x140018597  lea     rcx, [rbp+57h+var_A8]
0x14001859b  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x1400185a0  mov     r14, [rbx]
0x1400185a3  mov     [rbp+57h+var_A8], r14
0x1400185a7  mov     [rbx], r15
0x1400185aa  test    r14, r14
0x1400185ad  setnz   bl
0x1400185b0  lea     rcx, [rbp+57h+var_40]
0x1400185b4  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x1400185b9  test    bl, bl
0x1400185bb  jz      loc_140018C9C
0x1400185c1  mov     rax, [r14]
0x1400185c4  mov     rcx, r14
0x1400185c7  mov     rax, [rax+10h]
0x1400185cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400185d0  mov     rsi, rax
0x1400185d3  mov     rdx, [r14]
0x1400185d6  mov     rcx, r14
0x1400185d9  mov     rax, [rdx+8]
0x1400185dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400185e2  mov     rbx, rax
0x1400185e5  mov     [rbp+57h+EndPtr], rax
0x1400185e9  lea     rdx, aLevel; "level"
0x1400185f0  mov     rcx, rsi; String1
0x1400185f3  call    wcscmp_0
0x1400185f8  test    eax, eax
0x1400185fa  jnz     short loc_140018664
0x1400185fc  test    rbx, rbx
0x1400185ff  jz      loc_140018580
0x140018605  cmp     [rbx], r15w
0x140018609  jz      loc_140018580
0x14001860f  mov     [rbp+57h+EndPtr], r15
0x140018613  call    cs:__imp__o__errno
0x140018619  mov     [rax], r15d
0x14001861c  xor     r8d, r8d; Radix
0x14001861f  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x140018623  mov     rcx, rbx; String
0x140018626  call    cs:__imp_wcstoul
0x14001862c  mov     ebx, eax
0x14001862e  mov     rcx, [rbp+57h+EndPtr]
0x140018632  cmp     [rcx], r15w
0x140018636  jnz     loc_1400189BC
0x14001863c  call    cs:__imp__o__errno
0x140018642  cmp     [rax], r15d
0x140018645  jnz     loc_1400189BC
0x14001864b  cmp     ebx, 0FFh
0x140018651  jbe     short loc_140018655
0x140018653  mov     bl, 0FFh
0x140018655  mov     [rdi+72h], bl
0x140018658  or      byte ptr [rdi+0F2h], 1
0x14001865f  jmp     loc_140018580
0x140018664  lea     rdx, aKeywords; "keywords"
0x14001866b  mov     rcx, rsi; String1
0x14001866e  call    wcscmp_0
0x140018673  test    eax, eax
0x140018675  jnz     short loc_1400186D7
0x140018677  test    rbx, rbx
0x14001867a  jz      loc_140018580
0x140018680  cmp     [rbx], r15w
0x140018684  jz      loc_140018580
0x14001868a  call    cs:__imp__o__errno
0x140018690  mov     [rax], r15d
0x140018693  mov     [rbp+57h+var_78], r15
0x140018697  xor     r8d, r8d
0x14001869a  lea     rdx, [rbp+57h+var_78]
0x14001869e  mov     rcx, rbx
0x1400186a1  call    cs:__imp__o__wcstoui64
0x1400186a7  mov     rbx, rax
0x1400186aa  mov     rcx, [rbp+57h+var_78]
0x1400186ae  cmp     [rcx], r15w
0x1400186b2  jnz     loc_140018A18
0x1400186b8  call    cs:__imp__o__errno
0x1400186be  cmp     [rax], r15d
0x1400186c1  jnz     loc_140018A18
0x1400186c7  mov     [rdi+40h], rbx
0x1400186cb  or      byte ptr [rdi+0F3h], 1
0x1400186d2  jmp     loc_140018580
0x1400186d7  lea     rdx, aControlguid_0; "controlGuid"
0x1400186de  mov     rcx, rsi; String1
0x1400186e1  call    wcscmp_0
0x1400186e6  test    eax, eax
0x1400186e8  jnz     short loc_14001872F
0x1400186ea  test    rbx, rbx
0x1400186ed  jz      loc_140018580
0x1400186f3  cmp     [rbx], r15w
0x1400186f7  jz      loc_140018580
0x1400186fd  xorps   xmm0, xmm0
0x140018700  movups  [rbp+57h+var_38], xmm0
0x140018704  lea     rdx, [rbp+57h+EndPtr]
0x140018708  lea     rcx, [rbp+57h+var_38]
0x14001870c  call    ??$string_to_guid@PEB_W@tlx@@YAPEB_WPEAU_GUID@@AEBQEB_W@Z; tlx::string_to_guid<wchar_t const *>(_GUID *,wchar_t const * const &)
0x140018711  test    rax, rax
0x140018714  jz      loc_140018A74
0x14001871a  movups  xmm0, [rbp+57h+var_38]
0x14001871e  movdqu  xmmword ptr [rdi+48h], xmm0
0x140018723  or      byte ptr [rdi+0F4h], 1
0x14001872a  jmp     loc_140018580
0x14001872f  lea     rdx, aBuffersize; "bufferSize"
0x140018736  mov     rcx, rsi; String1
0x140018739  call    wcscmp_0
0x14001873e  test    eax, eax
0x140018740  jnz     short loc_1400187A0
0x140018742  test    rbx, rbx
0x140018745  jz      loc_140018580
0x14001874b  cmp     [rbx], r15w
0x14001874f  jz      loc_140018580
0x140018755  call    cs:__imp__o__errno
0x14001875b  mov     [rax], r15d
0x14001875e  mov     [rbp+57h+var_70], r15
0x140018762  xor     r8d, r8d; Radix
0x140018765  lea     rdx, [rbp+57h+var_70]; EndPtr
0x140018769  mov     rcx, rbx; String
0x14001876c  call    cs:__imp_wcstoul
0x140018772  mov     ebx, eax
0x140018774  mov     rcx, [rbp+57h+var_70]
0x140018778  cmp     [rcx], r15w
0x14001877c  jnz     loc_140018AD0
0x140018782  call    cs:__imp__o__errno
0x140018788  cmp     [rax], r15d
0x14001878b  jnz     loc_140018AD0
0x140018791  mov     [rdi+58h], ebx
0x140018794  or      byte ptr [rdi+0F5h], 1
0x14001879b  jmp     loc_140018580
0x1400187a0  lea     rdx, aFilemax_0; "fileMax"
0x1400187a7  mov     rcx, rsi; String1
0x1400187aa  call    wcscmp_0
0x1400187af  test    eax, eax
0x1400187b1  jnz     short loc_140018811
0x1400187b3  test    rbx, rbx
0x1400187b6  jz      loc_140018580
0x1400187bc  cmp     [rbx], r15w
0x1400187c0  jz      loc_140018580
0x1400187c6  call    cs:__imp__o__errno
0x1400187cc  mov     [rax], r15d
0x1400187cf  mov     [rbp+57h+var_68], r15
0x1400187d3  xor     r8d, r8d; Radix
0x1400187d6  lea     rdx, [rbp+57h+var_68]; EndPtr
0x1400187da  mov     rcx, rbx; String
0x1400187dd  call    cs:__imp_wcstoul
0x1400187e3  mov     ebx, eax
0x1400187e5  mov     rcx, [rbp+57h+var_68]
0x1400187e9  cmp     [rcx], r15w
0x1400187ed  jnz     loc_140018B2C
0x1400187f3  call    cs:__imp__o__errno
0x1400187f9  cmp     [rax], r15d
0x1400187fc  jnz     loc_140018B2C
0x140018802  mov     [rdi+68h], ebx
0x140018805  or      byte ptr [rdi+0FCh], 1
0x14001880c  jmp     loc_140018580
0x140018811  lea     rdx, aMinbuffers_0; "minBuffers"
0x140018818  mov     rcx, rsi; String1
0x14001881b  call    wcscmp_0
0x140018820  test    eax, eax
0x140018822  jnz     short loc_140018882
0x140018824  test    rbx, rbx
0x140018827  jz      loc_140018580
0x14001882d  cmp     [rbx], r15w
0x140018831  jz      loc_140018580
0x140018837  call    cs:__imp__o__errno
0x14001883d  mov     [rax], r15d
0x140018840  mov     [rbp+57h+var_60], r15
0x140018844  xor     r8d, r8d; Radix
0x140018847  lea     rdx, [rbp+57h+var_60]; EndPtr
0x14001884b  mov     rcx, rbx; String
0x14001884e  call    cs:__imp_wcstoul
0x140018854  mov     ebx, eax
0x140018856  mov     rcx, [rbp+57h+var_60]
0x14001885a  cmp     [rcx], r15w
0x14001885e  jnz     loc_140018B88
0x140018864  call    cs:__imp__o__errno
0x14001886a  cmp     [rax], r15d
0x14001886d  jnz     loc_140018B88
0x140018873  mov     [rdi+5Ch], ebx
0x140018876  or      byte ptr [rdi+0F6h], 1
0x14001887d  jmp     loc_140018580
0x140018882  lea     rdx, aMaxbuffers; "maxBuffers"
0x140018889  mov     rcx, rsi; String1
0x14001888c  call    wcscmp_0
0x140018891  test    eax, eax
0x140018893  jnz     short loc_1400188F3
0x140018895  test    rbx, rbx
0x140018898  jz      loc_140018580
0x14001889e  cmp     [rbx], r15w
0x1400188a2  jz      loc_140018580
0x1400188a8  call    cs:__imp__o__errno
0x1400188ae  mov     [rax], r15d
0x1400188b1  mov     [rbp+57h+var_58], r15
0x1400188b5  xor     r8d, r8d; Radix
0x1400188b8  lea     rdx, [rbp+57h+var_58]; EndPtr
0x1400188bc  mov     rcx, rbx; String
0x1400188bf  call    cs:__imp_wcstoul
0x1400188c5  mov     ebx, eax
0x1400188c7  mov     rcx, [rbp+57h+var_58]
0x1400188cb  cmp     [rcx], r15w
0x1400188cf  jnz     loc_140018BE4
0x1400188d5  call    cs:__imp__o__errno
0x1400188db  cmp     [rax], r15d
0x1400188de  jnz     loc_140018BE4
0x1400188e4  mov     [rdi+60h], ebx
0x1400188e7  or      byte ptr [rdi+0F7h], 1
0x1400188ee  jmp     loc_140018580
0x1400188f3  lea     rdx, aLatency_0; "latency"
0x1400188fa  mov     rcx, rsi; String1
0x1400188fd  call    wcscmp_0
0x140018902  test    eax, eax
0x140018904  jnz     short loc_140018964
0x140018906  test    rbx, rbx
0x140018909  jz      loc_140018580
0x14001890f  cmp     [rbx], r15w
0x140018913  jz      loc_140018580
0x140018919  call    cs:__imp__o__errno
0x14001891f  mov     [rax], r15d
0x140018922  mov     [rbp+57h+var_50], r15
0x140018926  xor     r8d, r8d; Radix
0x140018929  lea     rdx, [rbp+57h+var_50]; EndPtr
0x14001892d  mov     rcx, rbx; String
0x140018930  call    cs:__imp_wcstoul
0x140018936  mov     ebx, eax
0x140018938  mov     rcx, [rbp+57h+var_50]
0x14001893c  cmp     [rcx], r15w
0x140018940  jnz     loc_140018C40
0x140018946  call    cs:__imp__o__errno
0x14001894c  cmp     [rax], r15d
0x14001894f  jnz     loc_140018C40
0x140018955  mov     [rdi+64h], ebx
0x140018958  or      byte ptr [rdi+0F8h], 1
0x14001895f  jmp     loc_140018580
0x140018964  lea     rdx, aClocktype_0; "clockType"
0x14001896b  mov     rcx, rsi; String1
0x14001896e  call    wcscmp_0
0x140018973  test    eax, eax
0x140018975  jnz     short loc_14001898E
0x140018977  mov     rcx, rbx
0x14001897a  call    ParseChannelClockType
0x14001897f  mov     [rdi+70h], al
0x140018982  or      byte ptr [rdi+0F9h], 1
0x140018989  jmp     loc_140018580
0x14001898e  lea     rdx, aSidtype_0; "sidType"
0x140018995  mov     rcx, rsi; String1
0x140018998  call    wcscmp_0
0x14001899d  test    eax, eax
0x14001899f  jnz     loc_140018580
0x1400189a5  mov     rcx, rbx
0x1400189a8  call    ParseChannelSidType
0x1400189ad  mov     [rdi+71h], al
0x1400189b0  or      byte ptr [rdi+0FAh], 1
0x1400189b7  jmp     loc_140018580
0x1400189bc  lea     rax, WPP_GLOBAL_Control
0x1400189c3  mov     ebx, 57h ; 'W'
0x1400189c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400189cf  cmp     rcx, rax
0x1400189d2  jz      short loc_1400189F6
0x1400189d4  test    byte ptr [rcx+1Ch], 4
0x1400189d8  jz      short loc_1400189F6
0x1400189da  cmp     byte ptr [rcx+19h], 2
0x1400189de  jb      short loc_1400189F6
0x1400189e0  lea     edx, [rbx-40h]
0x1400189e3  mov     r9d, ebx
0x1400189e6  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400189ed  mov     rcx, [rcx+10h]
0x1400189f1  call    WPP_SF_d
0x1400189f6  mov     r9d, 155h; int
0x1400189fc  mov     edx, ebx; unsigned int
0x1400189fe  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140018a02  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140018a07  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140018a0e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140018a12  call    _CxxThrowException_0
0x140018a18  lea     rax, WPP_GLOBAL_Control
0x140018a1f  mov     ebx, 57h ; 'W'
0x140018a24  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a2b  cmp     rcx, rax
0x140018a2e  jz      short loc_140018A52
0x140018a30  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
