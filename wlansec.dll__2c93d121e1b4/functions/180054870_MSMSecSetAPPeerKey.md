# MSMSecSetAPPeerKey

- ea: `0x180054870`
- end: `0x180054f3a`
- name: `MSMSecSetAPPeerKey`
- size: `1738`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x18000c730`
- `0x18000e620`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x18001a23c`
- `0x18001ecb8`
- `0x18001f29c`
- `0x180021fd0`
- `0x18003da94`
- `0x180051bd4`
- `0x180054870`
- `0x180058534`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800549f3`
- `MobileNetworking!ReleaseWriteLock` at `0x180054aa7`
- `MobileNetworking!ReleaseWriteLock` at `0x180054b6e`
- `MobileNetworking!ReleaseWriteLock` at `0x180054c2d`
- `MobileNetworking!ReleaseWriteLock` at `0x180054d16`
- `MobileNetworking!ReleaseWriteLock` at `0x180054e15`
- `MobileNetworking!ReleaseWriteLock` at `0x180054e98`
- `MobileNetworking!ReleaseWriteLock` at `0x1800549f3`
- `MobileNetworking!ReleaseWriteLock` at `0x180054aa7`
- `MobileNetworking!ReleaseWriteLock` at `0x180054b6e`
- `MobileNetworking!ReleaseWriteLock` at `0x180054c2d`
- `MobileNetworking!ReleaseWriteLock` at `0x180054d16`
- `MobileNetworking!ReleaseWriteLock` at `0x180054e15`
- `MobileNetworking!ReleaseWriteLock` at `0x180054e98`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MSMSecSetAPPeerKey(void *a1, __int64 a2, _DWORD *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  unsigned int v10; // eax
  unsigned int v11; // esi
  const char *v12; // r9
  struct MSMSEC_INTF_CONTEXT *v13; // rcx
  unsigned int MSMSecMemory; // eax
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // edi
  struct _AP_PEER_KEY *v18; // rcx
  unsigned int v19; // [rsp+20h] [rbp-58h]
  struct MSMSEC_INTF_CONTEXT *v20; // [rsp+30h] [rbp-48h] BYREF
  struct _AP_PEER_KEY *v21[2]; // [rsp+38h] [rbp-40h] BYREF
  char v22; // [rsp+48h] [rbp-30h]
  struct _AP_PEER_KEY **v23; // [rsp+50h] [rbp-28h]
  char v24; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = IncThreadCountAndCheckInitializedEx("MSMSecSetAPPeerKey", 2482);
  v7 = v6;
  if ( v6 )
  {
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x9B2,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
      (const char *)v6,
      v19);
    return v7;
  }
  if ( !a1 || !a3 || !a2 )
  {
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x9B7,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
      (const char *)0x57,
      v19);
    DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
    return 87;
  }
  if ( !(unsigned int)RawDataIsValid(a3 + 2) )
  {
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x9B8,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
      (const char *)0xD,
      v19);
    DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
    return 13;
  }
  try
  {
    v20 = 0;
    v10 = SecMgrValidateRefAndLockAdapter(a1, &v20);
    v11 = v10;
    if ( v10 )
    {
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x9BB,
        (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
        (const char *)v10,
        v19);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      return v11;
    }
    v21[1] = (struct _AP_PEER_KEY *)&v20;
    v22 = 1;
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v20 + 681), 17) )
    {
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x9C0,
        (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
        (const char *)0x139F,
        v19);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      return 5023;
    }
    if ( !(unsigned int)IntfIsInAPMode(v20) )
    {
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x9C1,
        (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
        (const char *)0x139F,
        v19);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      return 5023;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      v19 = (unsigned int)a1;
      WPP_SF_LqL(*((_QWORD *)WPP_GLOBAL_Control + 7), 282, WPP_GLOBAL_Control, *((unsigned int *)v13 + 624));
      v13 = v20;
    }
    if ( !*((_QWORD *)v13 + 348) )
    {
      TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      return 0;
    }
    v21[0] = 0;
    MSMSecMemory = AllocateMSMSecMemory(0x30u);
    v15 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x9D2,
        (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
        (const char *)MSMSecMemory,
        v19);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      return v15;
    }
    v23 = v21;
    v24 = 1;
    if ( (unsigned int)RawDataIsNonEmpty(a3 + 2) )
    {
      v16 = CopyKey((*a3 >> 1) & 1, a3 + 2, (char *)v21[0] + 32);
      v17 = v16;
      if ( v16 )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x9DB,
          (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
          (const char *)v16,
          v19);
        FreeMSMSecMemory(v21);
        TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
        TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
        SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
        DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
        return v17;
      }
      *((_DWORD *)v21[0] + 6) |= 2u;
      *((_DWORD *)v21[0] + 6) ^= (*a3 ^ *((_DWORD *)v21[0] + 6)) & 1;
    }
    v18 = v21[0];
    *((_DWORD *)v21[0] + 4) = *(_DWORD *)a2;
    *((_WORD *)v18 + 10) = *(_WORD *)(a2 + 4);
    if ( InsertIntoPeerKeyList(v21[0], (struct _LIST_ENTRY *)v20 + 169, (unsigned int *)v20 + 680) )
    {
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x9E3,
        (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
        (const char *)0x139F,
        v19);
      FreeMSMSecMemory(v21);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v20, (char *)v20 + 2512, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
      TraceAdapterId(*((_DWORD *)v20 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v20, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
      DecThreadCountEx("MSMSecSetAPPeerKey::<lambda_1>::operator ()", 2484);
      result = 5023;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Win32_Return_CaughtException(
                           retaddr,
                           (void *)0x9E8,
                           (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\msmsecapi.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180054870  mov     [rsp+arg_0], rbx
0x180054875  mov     [rsp+arg_8], rsi
0x18005487a  push    rdi
0x18005487b  push    r14
0x18005487d  push    r15
0x18005487f  sub     rsp, 60h
0x180054883  mov     rbx, r8
0x180054886  mov     r15, rdx
0x180054889  mov     r14, rcx
0x18005488c  mov     esi, 9B2h
0x180054891  mov     edx, esi; int
0x180054893  lea     rcx, aMsmsecsetappee_0; "MSMSecSetAPPeerKey"
0x18005489a  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18005489f  mov     edi, eax
0x1800548a1  test    eax, eax
0x1800548a3  jz      short loc_1800548C2
0x1800548a5  mov     rcx, [rsp+78h]; this
0x1800548aa  mov     r9d, eax; char *
0x1800548ad  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x1800548b4  mov     edx, esi; void *
0x1800548b6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800548bb  mov     eax, edi
0x1800548bd  jmp     loc_180054F23
0x1800548c2  mov     [rsp+78h+arg_19], 1
0x1800548ca  test    r14, r14
0x1800548cd  jz      loc_180054EE8
0x1800548d3  test    rbx, rbx
0x1800548d6  jz      loc_180054EE8
0x1800548dc  test    r15, r15
0x1800548df  jz      loc_180054EE8
0x1800548e5  lea     rdi, [rbx+8]
0x1800548e9  mov     rcx, rdi
0x1800548ec  call    RawDataIsValid
0x1800548f1  test    eax, eax
0x1800548f3  jnz     short loc_18005492A
0x1800548f5  mov     rcx, [rsp+78h]; this
0x1800548fa  lea     ebx, [rax+0Dh]
0x1800548fd  mov     r9d, ebx; char *
0x180054900  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054907  mov     edx, 9B8h; void *
0x18005490c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054911  nop
0x180054912  mov     edx, 9B4h; int
0x180054917  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x18005491e  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054923  mov     eax, ebx
0x180054925  jmp     loc_180054F23
0x18005492a  mov     [rsp+78h+var_48], 0
0x180054933  lea     rdx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT **
0x180054938  mov     rcx, r14; void *
0x18005493b  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180054940  mov     esi, eax
0x180054942  test    eax, eax
0x180054944  jz      short loc_180054978
0x180054946  mov     rcx, [rsp+78h]; this
0x18005494b  mov     r9d, eax; char *
0x18005494e  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054955  mov     edx, 9BBh; void *
0x18005495a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005495f  nop
0x180054960  mov     edx, 9B4h; int
0x180054965  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x18005496c  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054971  mov     eax, esi
0x180054973  jmp     loc_180054F23
0x180054978  lea     rax, [rsp+78h+var_48]
0x18005497d  mov     [rsp+78h+var_38], rax
0x180054982  mov     [rsp+78h+var_30], 1
0x180054987  mov     edx, 11h
0x18005498c  mov     rcx, [rsp+78h+var_48]
0x180054991  mov     ecx, [rcx+0AA4h]
0x180054997  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18005499c  test    eax, eax
0x18005499e  jnz     loc_180054A46
0x1800549a4  mov     rcx, [rsp+78h]; this
0x1800549a9  mov     ebx, 139Fh
0x1800549ae  mov     r9d, ebx; char *
0x1800549b1  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x1800549b8  mov     edx, 9C0h; void *
0x1800549bd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800549c2  nop
0x1800549c3  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800549ca  mov     rcx, [rsp+78h+var_48]
0x1800549cf  mov     ecx, [rcx+9C0h]; unsigned int
0x1800549d5  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800549da  mov     rcx, [rsp+78h+var_48]
0x1800549df  lea     rdx, [rcx+9D0h]
0x1800549e6  mov     r9d, 9BDh
0x1800549ec  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x1800549f3  call    cs:__imp_ReleaseWriteLock
0x1800549fa  nop     dword ptr [rax+rax+00h]
0x1800549ff  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180054a06  mov     rcx, [rsp+78h+var_48]
0x180054a0b  mov     ecx, [rcx+9C0h]; unsigned int
0x180054a11  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054a16  mov     r8d, 9BEh; int
0x180054a1c  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054a23  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054a28  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054a2d  nop
0x180054a2e  mov     edx, 9B4h; int
0x180054a33  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x180054a3a  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054a3f  mov     eax, ebx
0x180054a41  jmp     loc_180054F23
0x180054a46  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054a4b  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x180054a50  test    eax, eax
0x180054a52  jnz     loc_180054AFA
0x180054a58  mov     rcx, [rsp+78h]; this
0x180054a5d  mov     ebx, 139Fh
0x180054a62  mov     r9d, ebx; char *
0x180054a65  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054a6c  mov     edx, 9C1h; void *
0x180054a71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054a76  nop
0x180054a77  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180054a7e  mov     rcx, [rsp+78h+var_48]
0x180054a83  mov     ecx, [rcx+9C0h]; unsigned int
0x180054a89  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054a8e  mov     rcx, [rsp+78h+var_48]
0x180054a93  lea     rdx, [rcx+9D0h]
0x180054a9a  mov     r9d, 9BDh
0x180054aa0  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054aa7  call    cs:__imp_ReleaseWriteLock
0x180054aae  nop     dword ptr [rax+rax+00h]
0x180054ab3  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180054aba  mov     rcx, [rsp+78h+var_48]
0x180054abf  mov     ecx, [rcx+9C0h]; unsigned int
0x180054ac5  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054aca  mov     r8d, 9BEh; int
0x180054ad0  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054ad7  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054adc  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054ae1  nop
0x180054ae2  mov     edx, 9B4h; int
0x180054ae7  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x180054aee  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054af3  mov     eax, ebx
0x180054af5  jmp     loc_180054F23
0x180054afa  lea     rax, WPP_GLOBAL_Control
0x180054b01  mov     r8, cs:WPP_GLOBAL_Control
0x180054b08  cmp     r8, rax
0x180054b0b  jz      short loc_180054B39
0x180054b0d  test    byte ptr [r8+44h], 20h
0x180054b12  jz      short loc_180054B39
0x180054b14  mov     edx, 11Ah
0x180054b19  mov     eax, [rdi]
0x180054b1b  mov     [rsp+78h+var_50], eax
0x180054b1f  mov     qword ptr [rsp+78h+var_58], r14; unsigned int
0x180054b24  mov     r9d, [rcx+9C0h]
0x180054b2b  mov     rcx, [r8+38h]
0x180054b2f  call    WPP_SF_LqL
0x180054b34  mov     rcx, [rsp+78h+var_48]
0x180054b39  cmp     qword ptr [rcx+0AE0h], 0
0x180054b41  jnz     short loc_180054BC1
0x180054b43  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180054b4a  mov     ecx, [rcx+9C0h]; unsigned int
0x180054b50  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054b55  mov     rcx, [rsp+78h+var_48]
0x180054b5a  lea     rdx, [rcx+9D0h]
0x180054b61  mov     r9d, 9BDh
0x180054b67  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054b6e  call    cs:__imp_ReleaseWriteLock
0x180054b75  nop     dword ptr [rax+rax+00h]
0x180054b7a  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180054b81  mov     rcx, [rsp+78h+var_48]
0x180054b86  mov     ecx, [rcx+9C0h]; unsigned int
0x180054b8c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054b91  mov     r8d, 9BEh; int
0x180054b97  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054b9e  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054ba3  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054ba8  nop
0x180054ba9  mov     edx, 9B4h; int
0x180054bae  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x180054bb5  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054bba  xor     eax, eax
0x180054bbc  jmp     loc_180054F23
0x180054bc1  mov     [rsp+78h+var_40], 0
0x180054bca  lea     rdx, [rsp+78h+var_40]
0x180054bcf  mov     ecx, 30h ; '0'; dwBytes
0x180054bd4  call    AllocateMSMSecMemory
0x180054bd9  mov     esi, eax
0x180054bdb  test    eax, eax
0x180054bdd  jz      loc_180054C80
0x180054be3  mov     rcx, [rsp+78h]; this
0x180054be8  mov     r9d, eax; char *
0x180054beb  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054bf2  mov     edx, 9D2h; void *
0x180054bf7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054bfc  nop
0x180054bfd  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180054c04  mov     rcx, [rsp+78h+var_48]
0x180054c09  mov     ecx, [rcx+9C0h]; unsigned int
0x180054c0f  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054c14  mov     rcx, [rsp+78h+var_48]
0x180054c19  lea     rdx, [rcx+9D0h]
0x180054c20  mov     r9d, 9BDh
0x180054c26  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054c2d  call    cs:__imp_ReleaseWriteLock
0x180054c34  nop     dword ptr [rax+rax+00h]
0x180054c39  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180054c40  mov     rcx, [rsp+78h+var_48]
0x180054c45  mov     ecx, [rcx+9C0h]; unsigned int
0x180054c4b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054c50  mov     r8d, 9BEh; int
0x180054c56  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054c5d  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054c62  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054c67  nop
0x180054c68  mov     edx, 9B4h; int
0x180054c6d  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x180054c74  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054c79  mov     eax, esi
0x180054c7b  jmp     loc_180054F23
0x180054c80  lea     rax, [rsp+78h+var_40]
0x180054c85  mov     [rsp+78h+var_28], rax
0x180054c8a  mov     [rsp+78h+var_20], 1
0x180054c8f  mov     rcx, rdi
0x180054c92  call    RawDataIsNonEmpty
0x180054c97  test    eax, eax
0x180054c99  jz      loc_180054D82
0x180054c9f  mov     r8, [rsp+78h+var_40]
0x180054ca4  add     r8, 20h ; ' '
0x180054ca8  mov     ecx, [rbx]
0x180054caa  shr     ecx, 1
0x180054cac  and     ecx, 1
0x180054caf  mov     rdx, rdi
0x180054cb2  call    CopyKey
0x180054cb7  mov     edi, eax
0x180054cb9  test    eax, eax
0x180054cbb  jz      loc_180054D69
0x180054cc1  mov     rcx, [rsp+78h]; this
0x180054cc6  mov     r9d, eax; char *
0x180054cc9  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054cd0  mov     edx, 9DBh; void *
0x180054cd5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054cda  nop
0x180054cdb  lea     rcx, [rsp+78h+var_40]
0x180054ce0  call    FreeMSMSecMemory
0x180054ce5  nop
0x180054ce6  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180054ced  mov     rcx, [rsp+78h+var_48]
0x180054cf2  mov     ecx, [rcx+9C0h]; unsigned int
0x180054cf8  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054cfd  mov     rcx, [rsp+78h+var_48]
0x180054d02  lea     rdx, [rcx+9D0h]
0x180054d09  mov     r9d, 9BDh
0x180054d0f  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054d16  call    cs:__imp_ReleaseWriteLock
0x180054d1d  nop     dword ptr [rax+rax+00h]
0x180054d22  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180054d29  mov     rcx, [rsp+78h+var_48]
0x180054d2e  mov     ecx, [rcx+9C0h]; unsigned int
0x180054d34  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054d39  mov     r8d, 9BEh; int
0x180054d3f  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180054d46  mov     rcx, [rsp+78h+var_48]; struct MSMSEC_INTF_CONTEXT *
0x180054d4b  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054d50  nop
0x180054d51  mov     edx, 9B4h; int
0x180054d56  lea     rcx, aMsmsecsetappee_1; "MSMSecSetAPPeerKey::<lambda_1>::operato"...
0x180054d5d  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180054d62  mov     eax, edi
0x180054d64  jmp     loc_180054F23
0x180054d69  mov     rax, [rsp+78h+var_40]
0x180054d6e  or      dword ptr [rax+18h], 2
0x180054d72  mov     rcx, [rsp+78h+var_40]
0x180054d77  mov     eax, [rcx+18h]
0x180054d7a  xor     eax, [rbx]
0x180054d7c  and     eax, 1
0x180054d7f  xor     [rcx+18h], eax
0x180054d82  mov     rcx, [rsp+78h+var_40]
0x180054d87  mov     eax, [r15]
0x180054d8a  mov     [rcx+10h], eax
0x180054d8d  movzx   eax, word ptr [r15+4]
0x180054d92  mov     [rcx+14h], ax
0x180054d96  mov     rdx, [rsp+78h+var_48]
0x180054d9b  lea     r8, [rdx+0AA0h]; unsigned int *
0x180054da2  add     rdx, 0A90h; struct _LIST_ENTRY *
0x180054da9  mov     rcx, [rsp+78h+var_40]; struct _AP_PEER_KEY *
0x180054dae  call    ?InsertIntoPeerKeyList@@YA_NPEAU_AP_PEER_KEY@@PEAU_LIST_ENTRY@@AEAK@Z; InsertIntoPeerKeyList(_AP_PEER_KEY *,_LIST_ENTRY *,ulong &)
0x180054db3  test    al, al
0x180054db5  jnz     loc_180054E68
0x180054dbb  mov     rcx, [rsp+78h]; this
0x180054dc0  mov     ebx, 139Fh
0x180054dc5  mov     r9d, ebx; char *
0x180054dc8  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\msmsec\\src\\msm"...
0x180054dcf  mov     edx, 9E3h; void *
0x180054dd4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054dd9  nop
0x180054dda  lea     rcx, [rsp+78h+var_40]
0x180054ddf  call    FreeMSMSecMemory
0x180054de4  nop
0x180054de5  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180054dec  mov     rcx, [rsp+78h+var_48]
0x180054df1  mov     ecx, [rcx+9C0h]; unsigned int
0x180054df7  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054dfc  mov     rcx, [rsp+78h+var_48]
  ... truncated ...
```
