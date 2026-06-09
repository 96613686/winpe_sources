# GetStreamForBuffer(uchar const *,unsigned __int64,IStream * *)

- ea: `0x1800619dc`
- end: `0x180061d0c`
- name: `?GetStreamForBuffer@@YAJPEBE_KPEAPEAUIStream@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(const unsigned __int8 *, SIZE_T, struct IStream **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061670`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18002e0b4`
- `0x1800619dc`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180061a67`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180061a67`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180061a79`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180061a79`

## string_xrefs

- `0x180061ab5`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x180061b4c`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x180061bd7`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x180061c69`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall GetStreamForBuffer(const unsigned __int8 *a1, SIZE_T a2, struct IStream **a3)
{
  PVOID v6; // rcx
  HGLOBAL v7; // rax
  HRESULT v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // esi
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  int v21; // [rsp+90h] [rbp+50h] BYREF
  LPSTREAM ppstm; // [rsp+98h] [rbp+58h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids);
  }
  ppstm = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !a3 || *a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  *a3 = 0;
  v7 = GlobalAlloc(2u, a2);
  v8 = CreateStreamOnHGlobal(v7, 1, &ppstm);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v21 = 0;
    v20 = 0;
    v12 = ULongLongToULong(a2, &v20);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = v20;
      v14 = (*(__int64 (__fastcall **)(LPSTREAM, const unsigned __int8 *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
              ppstm,
              a1,
              v20,
              &v21);
      v9 = v14;
      if ( v14 >= 0 )
      {
        if ( v21 != v13 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v15);
        v16 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
        v9 = v16;
        if ( v16 >= 0 )
        {
          *a3 = ppstm;
          ppstm = 0;
          goto LABEL_46;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
            (unsigned int)v16);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
          (const char *)v9,
          v18);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v11 = 18;
          goto LABEL_18;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
            (unsigned int)v14);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
          (const char *)v9,
          v18);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v11 = 16;
          goto LABEL_18;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
          (unsigned int)v12);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
        (const char *)v9,
        v18);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 14;
        goto LABEL_18;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
        (unsigned int)v8);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
      (const char *)v9,
      v18);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 12;
LABEL_18:
      WPP_SF_d(v10[2], v11, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v9);
LABEL_46:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    ppstm = 0;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 19, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800619dc  push    rbp
0x1800619de  push    rbx
0x1800619df  push    rsi
0x1800619e0  push    rdi
0x1800619e1  push    r12
0x1800619e3  push    r13
0x1800619e5  push    r14
0x1800619e7  mov     rbp, rsp
0x1800619ea  sub     rsp, 40h
0x1800619ee  mov     rdi, r8
0x1800619f1  mov     rsi, rdx
0x1800619f4  mov     r14, rcx
0x1800619f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800619fe  lea     r12, WPP_GLOBAL_Control
0x180061a05  lea     r13, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids
0x180061a0c  cmp     rcx, r12
0x180061a0f  jz      short loc_180061A2E
0x180061a11  test    byte ptr [rcx+1Ch], 4
0x180061a15  jz      short loc_180061A2E
0x180061a17  cmp     byte ptr [rcx+19h], 6
0x180061a1b  jb      short loc_180061A2E
0x180061a1d  mov     rcx, [rcx+10h]
0x180061a21  mov     edx, 0Ah
0x180061a26  mov     r8, r13
0x180061a29  call    WPP_SF_
0x180061a2e  mov     [rbp+ppstm], 0
0x180061a36  mov     [rbp+var_10], 0
0x180061a3e  test    r14, r14
0x180061a41  jnz     short loc_180061A48
0x180061a43  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061a48  test    rdi, rdi
0x180061a4b  jz      short loc_180061A53
0x180061a4d  cmp     qword ptr [rdi], 0
0x180061a51  jz      short loc_180061A58
0x180061a53  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061a58  mov     rdx, rsi; dwBytes
0x180061a5b  mov     qword ptr [rdi], 0
0x180061a62  mov     ecx, 2; uFlags
0x180061a67  call    cs:__imp_GlobalAlloc
0x180061a6d  lea     r8, [rbp+ppstm]; ppstm
0x180061a71  mov     edx, 1; fDeleteOnRelease
0x180061a76  mov     rcx, rax; hGlobal
0x180061a79  call    cs:__imp_CreateStreamOnHGlobal
0x180061a7f  mov     ebx, eax
0x180061a81  test    eax, eax
0x180061a83  jns     short loc_180061AFC
0x180061a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a8c  cmp     rcx, r12
0x180061a8f  jz      short loc_180061AB1
0x180061a91  test    byte ptr [rcx+1Ch], 4
0x180061a95  jz      short loc_180061AB1
0x180061a97  cmp     byte ptr [rcx+19h], 2
0x180061a9b  jb      short loc_180061AB1
0x180061a9d  mov     rcx, [rcx+10h]
0x180061aa1  mov     edx, 0Bh
0x180061aa6  mov     r9d, eax
0x180061aa9  mov     r8, r13
0x180061aac  call    WPP_SF_d
0x180061ab1  mov     rcx, [rbp+38h]; this
0x180061ab5  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061abc  mov     r9d, ebx; char *
0x180061abf  mov     edx, 43h ; 'C'; void *
0x180061ac4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180061ad0  cmp     rcx, r12
0x180061ad3  jz      loc_180061CAF
0x180061ad9  test    byte ptr [rcx+1Ch], 80h
0x180061add  jz      loc_180061CAF
0x180061ae3  mov     edx, 0Ch
0x180061ae8  mov     rcx, [rcx+10h]
0x180061aec  mov     r9d, ebx
0x180061aef  mov     r8, r13
0x180061af2  call    WPP_SF_d
0x180061af7  jmp     loc_180061CA8
0x180061afc  lea     rdx, [rbp+arg_0]; unsigned int *
0x180061b00  mov     [rbp+arg_10], 0
0x180061b07  mov     rcx, rsi; unsigned __int64
0x180061b0a  mov     [rbp+arg_0], 0
0x180061b11  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180061b16  mov     ebx, eax
0x180061b18  test    eax, eax
0x180061b1a  jns     short loc_180061B84
0x180061b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b23  cmp     rcx, r12
0x180061b26  jz      short loc_180061B48
0x180061b28  test    byte ptr [rcx+1Ch], 4
0x180061b2c  jz      short loc_180061B48
0x180061b2e  cmp     byte ptr [rcx+19h], 2
0x180061b32  jb      short loc_180061B48
0x180061b34  mov     rcx, [rcx+10h]
0x180061b38  mov     edx, 0Dh
0x180061b3d  mov     r9d, eax
0x180061b40  mov     r8, r13
0x180061b43  call    WPP_SF_d
0x180061b48  mov     rcx, [rbp+38h]; this
0x180061b4c  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061b53  mov     r9d, ebx; char *
0x180061b56  mov     edx, 4Ch ; 'L'; void *
0x180061b5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b67  cmp     rcx, r12
0x180061b6a  jz      loc_180061CAF
0x180061b70  test    byte ptr [rcx+1Ch], 80h
0x180061b74  jz      loc_180061CAF
0x180061b7a  mov     edx, 0Eh
0x180061b7f  jmp     loc_180061AE8
0x180061b84  mov     rcx, [rbp+ppstm]
0x180061b88  lea     r9, [rbp+arg_10]
0x180061b8c  mov     esi, [rbp+arg_0]
0x180061b8f  mov     rdx, r14
0x180061b92  mov     r8d, esi
0x180061b95  mov     rax, [rcx]
0x180061b98  mov     rax, [rax+20h]
0x180061b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ba1  mov     ebx, eax
0x180061ba3  test    eax, eax
0x180061ba5  jns     short loc_180061C0F
0x180061ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bae  cmp     rcx, r12
0x180061bb1  jz      short loc_180061BD3
0x180061bb3  test    byte ptr [rcx+1Ch], 4
0x180061bb7  jz      short loc_180061BD3
0x180061bb9  cmp     byte ptr [rcx+19h], 2
0x180061bbd  jb      short loc_180061BD3
0x180061bbf  mov     rcx, [rcx+10h]
0x180061bc3  mov     edx, 0Fh
0x180061bc8  mov     r9d, eax
0x180061bcb  mov     r8, r13
0x180061bce  call    WPP_SF_d
0x180061bd3  mov     rcx, [rbp+38h]; this
0x180061bd7  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061bde  mov     r9d, ebx; char *
0x180061be1  mov     edx, 50h ; 'P'; void *
0x180061be6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bf2  cmp     rcx, r12
0x180061bf5  jz      loc_180061CAF
0x180061bfb  test    byte ptr [rcx+1Ch], 80h
0x180061bff  jz      loc_180061CAF
0x180061c05  mov     edx, 10h
0x180061c0a  jmp     loc_180061AE8
0x180061c0f  cmp     [rbp+arg_10], esi
0x180061c12  jz      short loc_180061C19
0x180061c14  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061c19  mov     rcx, [rbp+ppstm]
0x180061c1d  xor     r9d, r9d
0x180061c20  mov     rdx, [rbp+var_10]
0x180061c24  xor     r8d, r8d
0x180061c27  mov     rax, [rcx]
0x180061c2a  mov     rax, [rax+28h]
0x180061c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c33  mov     ebx, eax
0x180061c35  test    eax, eax
0x180061c37  jns     short loc_180061C99
0x180061c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c40  cmp     rcx, r12
0x180061c43  jz      short loc_180061C65
0x180061c45  test    byte ptr [rcx+1Ch], 4
0x180061c49  jz      short loc_180061C65
0x180061c4b  cmp     byte ptr [rcx+19h], 2
0x180061c4f  jb      short loc_180061C65
0x180061c51  mov     rcx, [rcx+10h]
0x180061c55  mov     edx, 11h
0x180061c5a  mov     r9d, eax
0x180061c5d  mov     r8, r13
0x180061c60  call    WPP_SF_d
0x180061c65  mov     rcx, [rbp+38h]; this
0x180061c69  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061c70  mov     r9d, ebx; char *
0x180061c73  mov     edx, 55h ; 'U'; void *
0x180061c78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c84  cmp     rcx, r12
0x180061c87  jz      short loc_180061CAF
0x180061c89  test    byte ptr [rcx+1Ch], 80h
0x180061c8d  jz      short loc_180061CAF
0x180061c8f  mov     edx, 12h
0x180061c94  jmp     loc_180061AE8
0x180061c99  mov     rax, [rbp+ppstm]
0x180061c9d  mov     [rdi], rax
0x180061ca0  mov     [rbp+ppstm], 0
0x180061ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180061caf  mov     rdx, [rbp+ppstm]
0x180061cb3  test    rdx, rdx
0x180061cb6  jz      short loc_180061CD6
0x180061cb8  mov     rax, [rdx]
0x180061cbb  mov     rcx, rdx
0x180061cbe  mov     rax, [rax+10h]
0x180061cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180061cce  mov     [rbp+ppstm], 0
0x180061cd6  cmp     rcx, r12
0x180061cd9  jz      short loc_180061CFB
0x180061cdb  test    byte ptr [rcx+1Ch], 4
0x180061cdf  jz      short loc_180061CFB
0x180061ce1  cmp     byte ptr [rcx+19h], 6
0x180061ce5  jb      short loc_180061CFB
0x180061ce7  mov     rcx, [rcx+10h]
0x180061ceb  mov     edx, 13h
0x180061cf0  mov     r9d, ebx
0x180061cf3  mov     r8, r13
0x180061cf6  call    WPP_SF_d
0x180061cfb  mov     eax, ebx
0x180061cfd  add     rsp, 40h
0x180061d01  pop     r14
0x180061d03  pop     r13
0x180061d05  pop     r12
0x180061d07  pop     rdi
0x180061d08  pop     rsi
0x180061d09  pop     rbx
0x180061d0a  pop     rbp
0x180061d0b  retn
```
