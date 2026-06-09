# NotifWorker(void *)

- ea: `0x180028ae0`
- end: `0x180028ead`
- name: `?NotifWorker@@YAKPEAX@Z`
- size: `973`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000e620`
- `0x180028ae0`
- `0x180028ff4`
- `0x18003823c`
- `0x180043a30`
- `0x180050da8`
- `0x180096010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028d59`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028d59`

## string_xrefs

- `0x180028c90`: `Security`

## pseudocode

```c
__int64 __fastcall NotifWorker(_DWORD *Parameter, __int64 a2, __int64 a3, const struct _GUID *a4)
{
  PVOID *v5; // rcx
  int v6; // edx
  int v7; // r8d
  int v8; // r10d
  __int64 (__fastcall *v9)(__int64, __int64, _OWORD *); // r14
  __int64 v10; // rbx
  __int64 v11; // rsi
  PVOID *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v16; // r9
  PVOID *v17; // rcx
  const wchar_t *v19; // r9
  _DWORD *v20; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v21[2]; // [rsp+48h] [rbp-11h] BYREF
  char *v22; // [rsp+68h] [rbp+Fh]
  GUID ActivityId; // [rsp+70h] [rbp+17h] BYREF

  v20 = Parameter;
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Parameter )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
      *(_QWORD *)&ActivityId.Data1 = Parameter;
      EventActivityIdControl(2u, &ActivityId);
    }
    v6 = Parameter[10];
    LODWORD(v21[0]) = v6;
    v7 = Parameter[11];
    DWORD1(v21[0]) = v7;
    *(_OWORD *)((char *)v21 + 8) = *((_OWORD *)Parameter + 1);
    v8 = Parameter[12];
    DWORD2(v21[1]) = v8;
    v22 = (char *)(Parameter + 13);
    v9 = (__int64 (__fastcall *)(__int64, __int64, _OWORD *))*((_QWORD *)Parameter + 4);
    v10 = *((_QWORD *)Parameter + 1);
    v11 = *(_QWORD *)Parameter;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 137, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
        v8 = DWORD2(v21[1]);
        v7 = DWORD1(v21[0]);
        v6 = v21[0];
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 0x40) != 0 )
      {
        if ( v6 == 2 )
        {
          v19 = L"Security";
        }
        else
        {
          v19 = L"Invalid";
          if ( v6 == 4 )
            v19 = L"802.1x";
        }
        WPP_SF_SDDqL((unsigned int)v12[7], v6, v7, (_DWORD)v19, v6, v7, v10, v8, v20);
      }
    }
    v13 = v9(v11, v10, v21);
    v14 = v13;
    if ( v13 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_13:
        if ( v14 && v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 1) != 0 )
          WPP_SF_d(v15[7], 12, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids, v14);
        goto LABEL_14;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_10:
        if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x100) != 0 )
        {
          WPP_SF_d(v15[7], 140, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v14);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_13;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 139, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v13);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v14 = 87;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
    WPP_SF_(v5[7], 11, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids);
LABEL_14:
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&ActivityId.Data1 = Parameter;
    EtwEx_tidActivityInfo(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStop, &ActivityId, a4, 0x14u);
  }
  FreeMSMSecMemory(&v20);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      24,
      (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
      (unsigned int)"NotifWorker",
      52);
  v16 = (unsigned int)_InterlockedDecrement(&dword_1800AEF94);
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v16);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x100) != 0 )
      WPP_SF_d(v17[7], 13, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180028ae0  mov     [rsp-8+arg_8], rbx
0x180028ae5  mov     [rsp-8+arg_10], rsi
0x180028aea  push    rbp
0x180028aeb  push    rdi
0x180028aec  push    r12
0x180028aee  push    r14
0x180028af0  push    r15
0x180028af2  lea     rbp, [rsp-37h]
0x180028af7  sub     rsp, 90h
0x180028afe  mov     rax, cs:__security_cookie
0x180028b05  xor     rax, rsp
0x180028b08  mov     [rbp+57h+var_30], rax
0x180028b0c  xorps   xmm0, xmm0
0x180028b0f  mov     [rbp+57h+var_70], rcx
0x180028b13  xor     eax, eax
0x180028b15  mov     rdi, rcx
0x180028b18  movups  [rbp+57h+var_68], xmm0
0x180028b1c  mov     [rbp+57h+var_48], rax
0x180028b20  movups  [rbp+57h+var_58], xmm0
0x180028b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b2b  lea     r15, WPP_GLOBAL_Control
0x180028b32  mov     r12d, 100h
0x180028b38  cmp     rcx, r15
0x180028b3b  jz      short loc_180028B47
0x180028b3d  test    [rcx+44h], r12d
0x180028b41  jnz     loc_180028CEF
0x180028b47  test    rdi, rdi
0x180028b4a  jz      loc_180028D10
0x180028b50  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180028b56  test    eax, eax
0x180028b58  jnz     loc_180028D40
0x180028b5e  mov     edx, [rdi+28h]
0x180028b61  lea     rax, [rdi+34h]
0x180028b65  mov     dword ptr [rbp+57h+var_68], edx
0x180028b68  mov     r8d, [rdi+2Ch]
0x180028b6c  mov     dword ptr [rbp+57h+var_68+4], r8d
0x180028b70  movups  xmm0, xmmword ptr [rdi+10h]
0x180028b74  movdqu  [rbp+57h+var_68+8], xmm0
0x180028b79  mov     r10d, [rdi+30h]
0x180028b7d  mov     dword ptr [rbp+57h+var_58+8], r10d
0x180028b81  mov     [rbp+57h+var_48], rax
0x180028b85  mov     r14, [rdi+20h]
0x180028b89  mov     rbx, [rdi+8]
0x180028b8d  mov     rsi, [rdi]
0x180028b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b97  cmp     rcx, r15
0x180028b9a  jnz     loc_180028C6A
0x180028ba0  lea     r8, [rbp+57h+var_68]
0x180028ba4  mov     rdx, rbx
0x180028ba7  mov     rcx, rsi
0x180028baa  mov     rax, r14
0x180028bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bb2  mov     ebx, eax
0x180028bb4  test    eax, eax
0x180028bb6  jnz     loc_180028CB8
0x180028bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bc3  cmp     rcx, r15
0x180028bc6  jz      short loc_180028BD2
0x180028bc8  test    [rcx+44h], r12d
0x180028bcc  jnz     loc_180028DB0
0x180028bd2  test    ebx, ebx
0x180028bd4  jnz     loc_180028DD4
0x180028bda  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180028be0  test    eax, eax
0x180028be2  jnz     loc_180028E04
0x180028be8  lea     rcx, [rbp+57h+var_70]
0x180028bec  call    FreeMSMSecMemory
0x180028bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bf8  mov     edi, 400h
0x180028bfd  cmp     rcx, r15
0x180028c00  jz      short loc_180028C0B
0x180028c02  test    [rcx+44h], edi
0x180028c05  jnz     loc_180028E46
0x180028c0b  or      r9d, 0FFFFFFFFh
0x180028c0f  lock xadd cs:dword_1800AEF94, r9d
0x180028c18  dec     r9d
0x180028c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c22  cmp     rcx, r15
0x180028c25  jz      short loc_180028C3F
0x180028c27  test    [rcx+44h], edi
0x180028c2a  jnz     loc_180028E6F
0x180028c30  cmp     rcx, r15
0x180028c33  jz      short loc_180028C3F
0x180028c35  test    [rcx+44h], r12d
0x180028c39  jnz     loc_180028E90
0x180028c3f  mov     eax, ebx
0x180028c41  mov     rcx, [rbp+57h+var_30]
0x180028c45  xor     rcx, rsp; StackCookie
0x180028c48  call    __security_check_cookie
0x180028c4d  lea     r11, [rsp+0B0h+var_20]
0x180028c55  mov     rbx, [r11+38h]
0x180028c59  mov     rsi, [r11+40h]
0x180028c5d  mov     rsp, r11
0x180028c60  pop     r15
0x180028c62  pop     r14
0x180028c64  pop     r12
0x180028c66  pop     rdi
0x180028c67  pop     rbp
0x180028c68  retn
0x180028c6a  test    [rcx+44h], r12d
0x180028c6e  jnz     loc_180028D6A
0x180028c74  cmp     rcx, r15
0x180028c77  jz      loc_180028BA0
0x180028c7d  test    byte ptr [rcx+44h], 40h
0x180028c81  jz      loc_180028BA0
0x180028c87  cmp     edx, 2
0x180028c8a  jnz     loc_180028D96
0x180028c90  lea     r9, aSecurity; "Security"
0x180028c97  mov     rcx, [rcx+38h]
0x180028c9b  mov     [rsp+0B0h+var_78], r10d
0x180028ca0  mov     [rsp+0B0h+var_80], rbx
0x180028ca5  mov     [rsp+0B0h+var_88], r8d
0x180028caa  mov     [rsp+0B0h+var_90], edx
0x180028cae  call    WPP_SF_SDDqL
0x180028cb3  jmp     loc_180028BA0
0x180028cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cbf  cmp     rcx, r15
0x180028cc2  jz      loc_180028BD2
0x180028cc8  test    byte ptr [rcx+44h], 1
0x180028ccc  jz      loc_180028BC3
0x180028cd2  mov     rcx, [rcx+38h]
0x180028cd6  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180028cdd  mov     edx, 8Bh
0x180028ce2  mov     r9d, ebx
0x180028ce5  call    WPP_SF_d
0x180028cea  jmp     loc_180028BBC
0x180028cef  mov     rcx, [rcx+38h]
0x180028cf3  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x180028cfa  mov     edx, 0Ah
0x180028cff  call    WPP_SF_
0x180028d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d0b  jmp     loc_180028B47
0x180028d10  mov     ebx, 57h ; 'W'
0x180028d15  cmp     rcx, r15
0x180028d18  jz      loc_180028BDA
0x180028d1e  test    byte ptr [rcx+44h], 1
0x180028d22  jz      loc_180028BDA
0x180028d28  mov     rcx, [rcx+38h]
0x180028d2c  lea     edx, [rbx-4Ch]
0x180028d2f  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x180028d36  call    WPP_SF_
0x180028d3b  jmp     loc_180028BDA
0x180028d40  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x180028d47  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180028d4b  mov     ecx, 2; ControlCode
0x180028d50  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180028d55  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x180028d59  call    cs:__imp_EventActivityIdControl
0x180028d60  nop     dword ptr [rax+rax+00h]
0x180028d65  jmp     loc_180028B5E
0x180028d6a  mov     rcx, [rcx+38h]
0x180028d6e  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180028d75  mov     edx, 89h
0x180028d7a  call    WPP_SF_
0x180028d7f  mov     r10d, dword ptr [rbp+57h+var_58+8]
0x180028d83  mov     r8d, dword ptr [rbp+57h+var_68+4]
0x180028d87  mov     edx, dword ptr [rbp+57h+var_68]
0x180028d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d91  jmp     loc_180028C74
0x180028d96  cmp     edx, 4
0x180028d99  lea     r9, aInvalid_0; "Invalid"
0x180028da0  lea     rax, a8021x; "802.1x"
0x180028da7  cmovz   r9, rax
0x180028dab  jmp     loc_180028C97
0x180028db0  mov     rcx, [rcx+38h]
0x180028db4  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180028dbb  mov     edx, 8Ch
0x180028dc0  mov     r9d, ebx
0x180028dc3  call    WPP_SF_d
0x180028dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dcf  jmp     loc_180028BD2
0x180028dd4  cmp     rcx, r15
0x180028dd7  jz      loc_180028BDA
0x180028ddd  test    byte ptr [rcx+44h], 1
0x180028de1  jz      loc_180028BDA
0x180028de7  mov     rcx, [rcx+38h]
0x180028deb  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x180028df2  mov     edx, 0Ch
0x180028df7  mov     r9d, ebx
0x180028dfa  call    WPP_SF_d
0x180028dff  jmp     loc_180028BDA
0x180028e04  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180028e0a  test    eax, eax
0x180028e0c  jz      loc_180028BE8
0x180028e12  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x180028e19  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x180028e20  lea     r8, [rbp+57h+ActivityId]; struct _GUID *
0x180028e24  lea     rdx, ActivityStop; EventDescriptor
0x180028e2b  mov     [rsp+0B0h+var_90], 14h; unsigned int
0x180028e33  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180028e38  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x180028e3c  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x180028e41  jmp     loc_180028BE8
0x180028e46  mov     rcx, [rcx+38h]
0x180028e4a  lea     r9, aNotifworker; "NotifWorker"
0x180028e51  mov     edx, 18h
0x180028e56  mov     [rsp+0B0h+var_90], 34h ; '4'
0x180028e5e  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180028e65  call    WPP_SF_sd
0x180028e6a  jmp     loc_180028C0B
0x180028e6f  mov     rcx, [rcx+38h]
0x180028e73  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180028e7a  mov     edx, 19h
0x180028e7f  call    WPP_SF_d
0x180028e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e8b  jmp     loc_180028C30
0x180028e90  mov     rcx, [rcx+38h]
0x180028e94  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x180028e9b  mov     edx, 0Dh
0x180028ea0  mov     r9d, ebx
0x180028ea3  call    WPP_SF_d
0x180028ea8  jmp     loc_180028C3F
```
