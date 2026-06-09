# PnP::_ProcessInterfaceArrival(PnP::CMiscDeviceInterface *,PnPServices::CPnPInterfaceEvent *)

- ea: `0x180004790`
- end: `0x180004b41`
- name: `?_ProcessInterfaceArrival@PnP@@YAJPEAVCMiscDeviceInterface@1@PEAVCPnPInterfaceEvent@PnPServices@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(PnP *this, const WCHAR *, struct PnPServices::CPnPInterfaceEvent *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x1800036e0`

## callees

- `0x1800033f0`
- `0x1800046c0`
- `0x180004790`
- `0x180017d74`
- `0x18001b404`
- `0x180032c46`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1800048be`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1800048be`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180004889`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800048fd`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180004889`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800048fd`

## pseudocode

```c
__int64 __fastcall PnP::_ProcessInterfaceArrival(
        PnP *this,
        const WCHAR *a2,
        struct PnPServices::CPnPInterfaceEvent *a3)
{
  volatile signed __int32 *v3; // rsi
  volatile signed __int32 *v6; // rax
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  char *v9; // rdi
  int v10; // r14d
  __int64 v11; // rax
  int v12; // eax
  DEVINST v13; // ecx
  BOOL v14; // esi
  int i; // edi
  int *v16; // r9
  int ShouldAutoplayOnSpecialInterface; // esi
  _DWORD *v18; // rax
  _DWORD *v19; // rdi
  unsigned __int16 *v20; // r9
  __int64 v21; // r10
  __int64 v22; // rax
  _WORD *v23; // r8
  __int64 v24; // rdx
  _WORD *v25; // rdx
  __int64 v26; // r9
  const WCHAR *v27; // rax
  __int64 v28; // rdx
  GUID *v29; // rax
  GUID v30; // xmm0
  struct _GUID Buffer; // [rsp+40h] [rbp-58h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-48h] BYREF

  v3 = (volatile signed __int32 *)((char *)this + 16);
  if ( !this )
    v3 = 0;
  v6 = (volatile signed __int32 *)operator new(0x20u);
  v8 = v6;
  if ( !v6 )
    return CNamedElemList<PnP::CMiscDeviceInterface>::Remove<unsigned short const *>(v7, a2 + 10);
  v9 = (char *)this + 32;
  v10 = 1;
  *((_DWORD *)v6 + 2) = 1;
  *(_QWORD *)v6 = &PnPHelper::CPnPDeviceProperties::`vftable';
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 2) = v9;
  _InterlockedIncrement(v3 + 2);
  *((_QWORD *)v6 + 3) = v3;
  Buf2 = 0;
  v11 = *(_QWORD *)&guidInvalid.Data1 - *(_QWORD *)(v9 + 524);
  if ( *(_QWORD *)&guidInvalid.Data1 == *(_QWORD *)(v9 + 524) )
    v11 = *(_QWORD *)guidInvalid.Data4 - *(_QWORD *)(v9 + 532);
  if ( !v11 )
  {
    ShouldAutoplayOnSpecialInterface = -2147467259;
    goto LABEL_57;
  }
  v12 = *((_DWORD *)v9 + 137);
  Buf2 = *(GUID *)(v9 + 524);
  if ( v12 == 1 )
  {
    v13 = *(_DWORD *)v9;
    Buffer.Data1 = 4;
    if ( !CM_Get_DevNode_Registry_Property_ExW(v13, 0x10u, 0, v9 + 552, &Buffer.Data1, 0, 0) )
    {
      *((_DWORD *)v9 + 137) = 2;
      goto LABEL_18;
    }
    *((_DWORD *)v9 + 137) = 3;
LABEL_11:
    v14 = 0;
    goto LABEL_12;
  }
  if ( v12 != 2 )
    goto LABEL_11;
LABEL_18:
  v14 = (*((_DWORD *)v9 + 138) & 4) != 0;
  if ( (*((_DWORD *)v9 + 138) & 4) == 0 )
  {
LABEL_12:
    *(_DWORD *)&Buffer.Data2 = *(_DWORD *)v9;
    while ( !CM_Get_Parent((PDEVINST)&Buffer.Data2, *(DEVINST *)&Buffer.Data2, 0) )
    {
      Buffer.Data1 = 0;
      v14 = 0;
      *(_DWORD *)Buffer.Data4 = 4;
      if ( !CM_Get_DevNode_Registry_Property_ExW(
              *(DEVINST *)&Buffer.Data2,
              0x10u,
              0,
              &Buffer,
              (PULONG)Buffer.Data4,
              0,
              0) )
      {
        if ( (Buffer.Data1 & 4) != 0 )
          goto LABEL_20;
        Buffer.Data1 = 0;
      }
    }
  }
  if ( v14 )
  {
LABEL_20:
    for ( i = 0; ; i = 1 )
    {
      if ( i )
      {
        Buffer.Data1 = 0;
        goto LABEL_28;
      }
      if ( !memcmp_0(qword_18003E7D8, &Buf2, 0x10u) )
        break;
    }
    Buffer.Data1 = 1;
    ShouldAutoplayOnSpecialInterface = PnP::_ShouldAutoplayOnSpecialInterface((PnP *)v8, &Buf2, &Buffer, v16);
    if ( ShouldAutoplayOnSpecialInterface < 0 || !Buffer.Data1 )
      goto LABEL_57;
LABEL_28:
    v18 = operator new(0x2B8u);
    v19 = v18;
    if ( v18 )
    {
      v18[2] = 1;
      v20 = (unsigned __int16 *)(a2 + 10);
      *((_QWORD *)v18 + 85) = 0;
      v21 = 2147483646;
      *(_QWORD *)v18 = &Autoplay::CDispatchDeviceEvent::`vftable';
      v22 = 260;
      v23 = v19 + 8;
      v24 = 2147483646;
      do
      {
        if ( !v24 )
          break;
        v7 = *v20;
        if ( !(_WORD)v7 )
          break;
        *v23 = v7;
        ++v20;
        ++v23;
        --v24;
        --v22;
      }
      while ( v22 );
      v25 = v23 - 1;
      ShouldAutoplayOnSpecialInterface = -2147024774;
      if ( v22 )
        v25 = v23;
      v26 = 2147942522LL;
      if ( v22 )
        v26 = 0;
      *v25 = 0;
      if ( v22 )
      {
        v27 = L"DeviceArrival";
        v28 = 64;
        v23 = v19 + 138;
        do
        {
          if ( !v21 )
            break;
          if ( !*v27 )
            break;
          *v23++ = *v27++;
          --v21;
          --v28;
        }
        while ( v28 );
        v7 = (__int64)(v23 - 1);
        if ( v28 )
        {
          v7 = (__int64)v23;
          ShouldAutoplayOnSpecialInterface = 0;
        }
        *(_WORD *)v7 = 0;
        if ( v28 )
        {
          if ( v8 )
          {
            _InterlockedIncrement(v8 + 2);
            *((_QWORD *)v19 + 85) = v8;
          }
          v29 = &GUID_NULL;
          if ( a2 != (const WCHAR *)-540LL )
            v29 = (GUID *)(a2 + 270);
          v30 = *v29;
          v19[172] = 1;
          *((GUID *)v19 + 1) = v30;
          ShouldAutoplayOnSpecialInterface = Autoplay::DispatchDeviceEvent(
                                               (Autoplay *)v19,
                                               (struct Autoplay::CDispatchDeviceEvent *)v28);
        }
      }
      else
      {
        ShouldAutoplayOnSpecialInterface = v26;
      }
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(_DWORD *, __int64, _WORD *, __int64))v19)(v19, 1, v23, v26);
        v10 = 0;
        goto LABEL_57;
      }
    }
    else
    {
      ShouldAutoplayOnSpecialInterface = -2147024882;
    }
    v10 = 0;
  }
  else
  {
    ShouldAutoplayOnSpecialInterface = 0;
  }
LABEL_57:
  if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( v8 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v8)(v8, 1);
  }
  if ( !v10 )
    return (unsigned int)ShouldAutoplayOnSpecialInterface;
  return CNamedElemList<PnP::CMiscDeviceInterface>::Remove<unsigned short const *>(v7, a2 + 10);
}

```

## disassembly

```asm
0x180004790  push    rbx
0x180004792  push    rsi
0x180004793  push    rdi
0x180004794  push    r12
0x180004796  push    r15
0x180004798  sub     rsp, 70h
0x18000479c  mov     rax, cs:__security_cookie
0x1800047a3  xor     rax, rsp
0x1800047a6  mov     [rsp+98h+var_38], rax
0x1800047ab  lea     rsi, [rcx+10h]
0x1800047af  xor     r12d, r12d
0x1800047b2  test    rcx, rcx
0x1800047b5  mov     rdi, rcx
0x1800047b8  mov     ecx, 20h ; ' '; Size
0x1800047bd  mov     r15, rdx
0x1800047c0  cmovz   rsi, r12
0x1800047c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047c9  mov     rbx, rax
0x1800047cc  test    rax, rax
0x1800047cf  jz      loc_180004B1F
0x1800047d5  mov     [rsp+98h+arg_10], rbp
0x1800047dd  add     rdi, 20h ; ' '
0x1800047e1  mov     [rsp+98h+arg_18], r14
0x1800047e9  mov     r14d, 1
0x1800047ef  mov     [rax+8], r14d
0x1800047f3  lea     rax, ??_7CPnPDeviceProperties@PnPHelper@@6B@; const PnPHelper::CPnPDeviceProperties::`vftable'
0x1800047fa  mov     [rbx], rax
0x1800047fd  mov     [rbx+18h], r12
0x180004801  mov     [rbx+10h], rdi
0x180004805  lock inc dword ptr [rsi+8]
0x180004809  mov     [rbx+18h], rsi
0x18000480d  xorps   xmm0, xmm0
0x180004810  mov     rax, qword ptr cs:?guidInvalid@@3U_GUID@@B.Data1; _GUID const guidInvalid ...
0x180004817  movups  [rsp+98h+Buf2], xmm0
0x18000481c  sub     rax, [rdi+20Ch]
0x180004823  jnz     short loc_180004833
0x180004825  mov     rax, qword ptr cs:?guidInvalid@@3U_GUID@@B.Data4; _GUID const guidInvalid ...
0x18000482c  sub     rax, [rdi+214h]
0x180004833  mov     ebp, 0FFFFFFFFh
0x180004838  test    rax, rax
0x18000483b  jz      loc_180004ADF
0x180004841  movups  xmm0, xmmword ptr [rdi+20Ch]
0x180004848  mov     eax, [rdi+224h]
0x18000484e  movups  [rsp+98h+Buf2], xmm0
0x180004853  cmp     eax, r14d
0x180004856  jnz     loc_180004915
0x18000485c  mov     ecx, [rdi]; dnDevInst
0x18000485e  lea     rax, [rsp+98h+Buffer]
0x180004863  mov     [rsp+98h+hMachine], r12; hMachine
0x180004868  lea     r9, [rdi+228h]; Buffer
0x18000486f  mov     [rsp+98h+ulFlags], r12d; ulFlags
0x180004874  xor     r8d, r8d; pulRegDataType
0x180004877  mov     edx, 10h; ulProperty
0x18000487c  mov     [rsp+98h+pulLength], rax; pulLength
0x180004881  mov     [rsp+98h+Buffer], 4
0x180004889  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x18000488f  test    eax, eax
0x180004891  jnz     short loc_18000489F
0x180004893  mov     dword ptr [rdi+224h], 2
0x18000489d  jmp     short loc_18000491A
0x18000489f  mov     dword ptr [rdi+224h], 3
0x1800048a9  mov     esi, r12d
0x1800048ac  mov     eax, [rdi]
0x1800048ae  mov     [rsp+98h+pdnDevInst], eax
0x1800048b2  mov     edx, [rsp+98h+pdnDevInst]; dnDevInst
0x1800048b6  lea     rcx, [rsp+98h+pdnDevInst]; pdnDevInst
0x1800048bb  xor     r8d, r8d; ulFlags
0x1800048be  call    cs:__imp_CM_Get_Parent
0x1800048c4  test    eax, eax
0x1800048c6  jnz     short loc_180004935
0x1800048c8  mov     ecx, [rsp+98h+pdnDevInst]; dnDevInst
0x1800048cc  lea     rax, [rsp+98h+var_50]
0x1800048d1  mov     [rsp+98h+hMachine], r12; hMachine
0x1800048d6  lea     r9, [rsp+98h+Buffer]; Buffer
0x1800048db  mov     [rsp+98h+ulFlags], r12d; ulFlags
0x1800048e0  xor     r8d, r8d; pulRegDataType
0x1800048e3  mov     edx, 10h; ulProperty
0x1800048e8  mov     [rsp+98h+pulLength], rax; pulLength
0x1800048ed  mov     [rsp+98h+Buffer], r12d
0x1800048f2  mov     esi, r12d
0x1800048f5  mov     [rsp+98h+var_50], 4
0x1800048fd  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180004903  test    eax, eax
0x180004905  jnz     short loc_1800048B2
0x180004907  test    byte ptr [rsp+98h+Buffer], 4
0x18000490c  jnz     short loc_18000493D
0x18000490e  mov     [rsp+98h+Buffer], r12d
0x180004913  jmp     short loc_1800048B2
0x180004915  cmp     eax, 2
0x180004918  jnz     short loc_1800048A9
0x18000491a  mov     eax, [rdi+228h]
0x180004920  mov     esi, r12d
0x180004923  bt      eax, 2
0x180004927  setb    sil
0x18000492b  bt      eax, 2
0x18000492f  jnb     loc_1800048AC
0x180004935  test    esi, esi
0x180004937  jz      loc_180004ADA
0x18000493d  mov     edi, r12d
0x180004940  lea     rsi, qword_18003E7D8
0x180004947  cmp     edi, r14d
0x18000494a  jnb     short loc_18000499A
0x18000494c  mov     ecx, edi
0x18000494e  lea     rdx, [rsp+98h+Buf2]; Buf2
0x180004953  shl     rcx, 4
0x180004957  mov     r8d, 10h; Size
0x18000495d  add     rcx, rsi; Buf1
0x180004960  call    memcmp_0
0x180004965  test    eax, eax
0x180004967  jz      short loc_18000496D
0x180004969  inc     edi
0x18000496b  jmp     short loc_180004947
0x18000496d  lea     r8, [rsp+98h+Buffer]; struct _GUID *
0x180004972  mov     [rsp+98h+Buffer], r14d
0x180004977  lea     rdx, [rsp+98h+Buf2]; rguid
0x18000497c  mov     rcx, rbx; this
0x18000497f  call    ?_ShouldAutoplayOnSpecialInterface@PnP@@YAJPEAVIDeviceProperties@Autoplay@@AEBU_GUID@@PEAH@Z; PnP::_ShouldAutoplayOnSpecialInterface(Autoplay::IDeviceProperties *,_GUID const &,int *)
0x180004984  mov     esi, eax
0x180004986  test    eax, eax
0x180004988  js      loc_180004AE4
0x18000498e  cmp     [rsp+98h+Buffer], r12d
0x180004993  jnz     short loc_18000499F
0x180004995  jmp     loc_180004AE4
0x18000499a  mov     [rsp+98h+Buffer], r12d
0x18000499f  mov     ecx, 2B8h; Size
0x1800049a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049a9  mov     rdi, rax
0x1800049ac  test    rax, rax
0x1800049af  jz      loc_180004AD0
0x1800049b5  mov     [rax+8], r14d
0x1800049b9  lea     r9, [r15+14h]
0x1800049bd  lea     rax, ??_7CDispatchDeviceEvent@Autoplay@@6B@; const Autoplay::CDispatchDeviceEvent::`vftable'
0x1800049c4  mov     [rdi+2A8h], r12
0x1800049cb  mov     r10d, 7FFFFFFEh
0x1800049d1  mov     [rdi], rax
0x1800049d4  mov     eax, 104h
0x1800049d9  lea     r8, [rdi+20h]
0x1800049dd  mov     edx, r10d
0x1800049e0  test    rdx, rdx
0x1800049e3  jz      short loc_180004A02
0x1800049e5  movzx   ecx, word ptr [r9]
0x1800049e9  test    cx, cx
0x1800049ec  jz      short loc_180004A02
0x1800049ee  mov     [r8], cx
0x1800049f2  add     r9, 2
0x1800049f6  add     r8, 2
0x1800049fa  dec     rdx
0x1800049fd  sub     rax, r14
0x180004a00  jnz     short loc_1800049E0
0x180004a02  test    rax, rax
0x180004a05  lea     rdx, [r8-2]
0x180004a09  mov     esi, 8007007Ah
0x180004a0e  cmovnz  rdx, r8
0x180004a12  mov     r9d, esi
0x180004a15  cmovnz  r9d, r12d
0x180004a19  mov     [rdx], r12w
0x180004a1d  jz      loc_180004AAB
0x180004a23  lea     rax, aDevicearrival; "DeviceArrival"
0x180004a2a  mov     edx, 40h ; '@'
0x180004a2f  lea     r8, [rdi+228h]
0x180004a36  test    r10, r10
0x180004a39  jz      short loc_180004A57
0x180004a3b  movzx   ecx, word ptr [rax]
0x180004a3e  test    cx, cx
0x180004a41  jz      short loc_180004A57
0x180004a43  mov     [r8], cx
0x180004a47  add     rax, 2
0x180004a4b  add     r8, 2
0x180004a4f  dec     r10
0x180004a52  sub     rdx, r14; struct Autoplay::CDispatchDeviceEvent *
0x180004a55  jnz     short loc_180004A36
0x180004a57  test    rdx, rdx
0x180004a5a  lea     rcx, [r8-2]
0x180004a5e  cmovnz  rcx, r8
0x180004a62  cmovnz  esi, r12d
0x180004a66  mov     [rcx], r12w
0x180004a6a  jz      short loc_180004AAE
0x180004a6c  lea     rcx, [r15+21Ch]
0x180004a73  test    rbx, rbx
0x180004a76  jz      short loc_180004A83
0x180004a78  lock inc dword ptr [rbx+8]
0x180004a7c  mov     [rdi+2A8h], rbx
0x180004a83  test    rcx, rcx
0x180004a86  lea     rax, GUID_NULL
0x180004a8d  cmovnz  rax, rcx
0x180004a91  mov     rcx, rdi; this
0x180004a94  movups  xmm0, xmmword ptr [rax]
0x180004a97  mov     [rdi+2B0h], r14d
0x180004a9e  movups  xmmword ptr [rdi+10h], xmm0
0x180004aa2  call    ?DispatchDeviceEvent@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z; Autoplay::DispatchDeviceEvent(Autoplay::CDispatchDeviceEvent *)
0x180004aa7  mov     esi, eax
0x180004aa9  jmp     short loc_180004AAE
0x180004aab  mov     esi, r9d
0x180004aae  mov     eax, ebp
0x180004ab0  lock xadd [rdi+8], eax
0x180004ab5  cmp     eax, r14d
0x180004ab8  jnz     short loc_180004AD5
0x180004aba  mov     rax, [rdi]
0x180004abd  mov     edx, r14d
0x180004ac0  mov     rcx, rdi
0x180004ac3  mov     rax, [rax]
0x180004ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acb  mov     r14d, r12d
0x180004ace  jmp     short loc_180004AE4
0x180004ad0  mov     esi, 8007000Eh
0x180004ad5  mov     r14d, r12d
0x180004ad8  jmp     short loc_180004AE4
0x180004ada  mov     esi, r12d
0x180004add  jmp     short loc_180004AE4
0x180004adf  mov     esi, 80004005h
0x180004ae4  lock xadd [rbx+8], ebp
0x180004ae9  cmp     ebp, 1
0x180004aec  mov     rbp, [rsp+98h+arg_10]
0x180004af4  jnz     short loc_180004B0E
0x180004af6  test    rbx, rbx
0x180004af9  jz      short loc_180004B0E
0x180004afb  mov     rax, [rbx]
0x180004afe  mov     edx, 1
0x180004b03  mov     rcx, rbx
0x180004b06  mov     rax, [rax]
0x180004b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0e  test    r14d, r14d
0x180004b11  mov     r14, [rsp+98h+arg_18]
0x180004b19  jnz     short loc_180004B1F
0x180004b1b  mov     eax, esi
0x180004b1d  jmp     short loc_180004B28
0x180004b1f  lea     rdx, [r15+14h]
0x180004b23  call    ??$Remove@PEBG@?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@QEAAJQEBG@Z; CNamedElemList<PnP::CMiscDeviceInterface>::Remove<ushort const *>(ushort const * const)
0x180004b28  mov     rcx, [rsp+98h+var_38]
0x180004b2d  xor     rcx, rsp; StackCookie
0x180004b30  call    __security_check_cookie
0x180004b35  add     rsp, 70h
0x180004b39  pop     r15
0x180004b3b  pop     r12
0x180004b3d  pop     rdi
0x180004b3e  pop     rsi
0x180004b3f  pop     rbx
0x180004b40  retn
```
