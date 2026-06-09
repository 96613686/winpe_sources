# SxspComInterfaceRedirectionGuidSectionGenerationCallback(void *,ulong,void *)

- ea: `0x180037780`
- end: `0x180037b51`
- name: `?SxspComInterfaceRedirectionGuidSectionGenerationCallback@@YAHPEAXK0@Z`
- size: `977`
- prototype: `__int64 __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c2c8`
- `0x180036ab4`
- `0x180037780`
- `0x180058758`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18003785e`
- `ntdll!RtlPopFrame` at `0x180037a0d`
- `ntdll!RtlPopFrame` at `0x18003785e`
- `ntdll!RtlPopFrame` at `0x180037a0d`
- `ntdll!RtlPushFrame` at `0x1800377e3`
- `ntdll!RtlPushFrame` at `0x1800377e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037821`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037aa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037ac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037821`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037aa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037ac5`

## pseudocode

```c
__int64 __fastcall SxspComInterfaceRedirectionGuidSectionGenerationCallback(void *a1, int a2, _IID_ENTRY **a3)
{
  unsigned int v5; // edx
  _IID_ENTRY *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // ebx
  int v10; // edi
  __int64 v11; // rdi
  _IID_ENTRY *v12; // rsi
  _IID_ENTRY *v13; // r15
  int v14; // ecx
  int v15; // eax
  GUID v16; // xmm0
  _DWORD *v17; // r12
  _DWORD *v18; // r13
  size_t v19; // r14
  int v20; // esi
  _IID_ENTRY *v21; // rcx
  DWORD LastError; // eax
  DWORD v23; // eax
  unsigned __int64 v24; // [rsp+28h] [rbp-49h] BYREF
  char v25; // [rsp+30h] [rbp-41h]
  int v26; // [rsp+38h] [rbp-39h] BYREF
  int v27; // [rsp+3Ch] [rbp-35h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+40h] [rbp-31h] BYREF
  __int64 v29; // [rsp+58h] [rbp-19h]
  int v30; // [rsp+60h] [rbp-11h]
  unsigned int *v31; // [rsp+68h] [rbp-9h]
  struct _TEB_ACTIVE_FRAME v32; // [rsp+70h] [rbp-1h] BYREF
  __int64 v33; // [rsp+88h] [rbp+17h]
  int v34; // [rsp+90h] [rbp+1Fh]
  int *v35; // [rsp+98h] [rbp+27h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006FC10;
  v31 = (unsigned int *)&v27;
  v27 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v29 = 544438355;
  v30 = 417;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( a2 == 1 )
  {
    v6 = *a3;
    a3[1] = (_IID_ENTRY *)68;
    if ( v6 )
    {
      v7 = *((_QWORD *)v6 + 13);
      if ( v7 )
        a3[1] = (_IID_ENTRY *)(2 * v7 + 70);
    }
    goto LABEL_7;
  }
  v10 = a2 - 2;
  if ( v10 )
  {
    if ( v10 == 1 )
    {
      v21 = *a3;
      v24 = 0;
      v25 = 0;
      if ( v21 )
        _IID_ENTRY::`scalar deleting destructor'(v21, v5);
      CSmartPtr<_IID_ENTRY,CSmartPtrBaseTypeHelper<_IID_ENTRY>>::~CSmartPtr<_IID_ENTRY,CSmartPtrBaseTypeHelper<_IID_ENTRY>>(&v24);
    }
    goto LABEL_7;
  }
  v24 = (unsigned __int64)a3[2];
  if ( v24 < 0x44 )
  {
    SetLastError(0x7Au);
  }
  else
  {
    v11 = 68;
    v12 = a3[3];
    v13 = a3[1];
    *(_QWORD *)v12 = 68;
    *(_OWORD *)((char *)v12 + 8) = *(_OWORD *)v13;
    if ( *((_BYTE *)v13 + 632) )
    {
      *((_DWORD *)v12 + 1) = 1;
      v14 = 3;
      v15 = *((_DWORD *)v13 + 8);
    }
    else
    {
      v15 = 0;
      v14 = 2;
    }
    *((_DWORD *)v12 + 6) = v15;
    *(_OWORD *)((char *)v12 + 28) = *(_OWORD *)((char *)v13 + 36);
    if ( *((_BYTE *)v13 + 633) )
    {
      *((_DWORD *)v12 + 1) = v14;
      v16 = *(GUID *)((char *)v13 + 52);
    }
    else
    {
      v16 = GUID_NULL;
    }
    *(GUID *)((char *)v12 + 44) = v16;
    SetLastError(0);
    v26 = 0;
    v32.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer'::`2'::__stc;
    v32.Flags = 1;
    v35 = &v26;
    v17 = (_DWORD *)((char *)v12 + 60);
    v18 = (_DWORD *)((char *)v12 + 64);
    v32.Previous = 0;
    v33 = 544438355;
    v34 = 1422;
    CFrame::BaseEnter((CFrame *)&v32);
    if ( v12 != (_IID_ENTRY *)-64LL )
      *v18 = 0;
    if ( v12 != (_IID_ENTRY *)-60LL )
      *v17 = 0;
    v19 = *((_QWORD *)v13 + 13);
    if ( v19 && ((v19 = 2 * v19 + 2, v24 - 68 < v19) || v19 > 0xFFFFFFFF) )
    {
      SetLastError(0x7Au);
    }
    else
    {
      memcpy_0((char *)v12 + 68, *((const void **)v13 + 11), v19);
      if ( v12 != (_IID_ENTRY *)-64LL && v19 )
        *v18 = 68;
      if ( v12 != (_IID_ENTRY *)-60LL )
      {
        if ( v19 )
          *v17 = v19 - 2;
        else
          *v17 = 0;
      }
      v11 = v19 + 68;
      v26 = 1;
    }
    v20 = v26;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *v35 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        LastError = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
      }
    }
    RtlPopFrame(&v32);
    if ( v20 )
    {
      a3[4] = (_IID_ENTRY *)v11;
LABEL_7:
      SetLastError(0);
      *v31 = 1;
      goto LABEL_8;
    }
    *v31 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007BA60);
  }
LABEL_8:
  v8 = *v31;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v8 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v23 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v23, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v8;
}

```

## disassembly

```asm
0x180037780  mov     r11, rsp
0x180037783  push    rbp
0x180037784  push    rbx
0x180037785  lea     rbp, [r11-5Fh]
0x180037789  sub     rsp, 0B8h
0x180037790  mov     rax, cs:__security_cookie
0x180037797  xor     rax, rsp
0x18003779a  mov     [rbp+57h+var_28], rax
0x18003779e  mov     [r11+10h], rdi
0x1800377a2  lea     rax, qword_18006FC10
0x1800377a9  mov     [rbp+57h+Frame.Context], rax
0x1800377ad  lea     rcx, [rbp+57h+Frame]; Frame
0x1800377b1  mov     [r11-20h], r14
0x1800377b5  lea     rax, [rbp+57h+var_8C]
0x1800377b9  xor     r14d, r14d
0x1800377bc  mov     [rbp+57h+var_60], rax
0x1800377c0  mov     rbx, r8
0x1800377c3  mov     [rbp+57h+var_8C], r14d
0x1800377c7  mov     edi, edx
0x1800377c9  mov     [rbp+57h+Frame.Flags], 1
0x1800377d0  mov     [rbp+57h+Frame.Previous], r14
0x1800377d4  mov     [rbp+57h+var_70], 20737853h
0x1800377dc  mov     [rbp+57h+var_68], 1A1h
0x1800377e3  call    cs:__imp_RtlPushFrame
0x1800377ea  nop     dword ptr [rax+rax+00h]
0x1800377ef  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x1800377f6  jnz     loc_180037A4D
0x1800377fc  cmp     edi, 1
0x1800377ff  jnz     loc_180037891
0x180037805  mov     rax, [rbx]
0x180037808  mov     edi, 44h ; 'D'
0x18003780d  mov     [rbx+8], rdi
0x180037811  test    rax, rax
0x180037814  jz      short loc_18003781F
0x180037816  mov     rax, [rax+68h]
0x18003781a  test    rax, rax
0x18003781d  jnz     short loc_180037883
0x18003781f  xor     ecx, ecx; dwErrCode
0x180037821  call    cs:__imp_SetLastError
0x180037828  nop     dword ptr [rax+rax+00h]
0x18003782d  mov     rax, [rbp+57h+var_60]
0x180037831  mov     dword ptr [rax], 1
0x180037837  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18003783e  mov     rax, [rbp+57h+var_60]
0x180037842  mov     r14, [rsp+0C0h+var_18]
0x18003784a  mov     rdi, [rsp+0C0h+arg_8]
0x180037852  mov     ebx, [rax]
0x180037854  jnz     loc_180037B27
0x18003785a  lea     rcx, [rbp+57h+Frame]; Frame
0x18003785e  call    cs:__imp_RtlPopFrame
0x180037865  nop     dword ptr [rax+rax+00h]
0x18003786a  mov     eax, ebx
0x18003786c  mov     rcx, [rbp+57h+var_28]
0x180037870  xor     rcx, rsp; StackCookie
0x180037873  call    __security_check_cookie
0x180037878  add     rsp, 0B8h
0x18003787f  pop     rbx
0x180037880  pop     rbp
0x180037881  retn
0x180037883  lea     rax, ds:46h[rax*2]
0x18003788b  mov     [rbx+8], rax
0x18003788f  jmp     short loc_18003781F
0x180037891  sub     edi, 2
0x180037894  jnz     loc_180037A76
0x18003789a  mov     rax, [rbx+10h]
0x18003789e  mov     [rbp+57h+var_A0], rax
0x1800378a2  cmp     rax, 44h ; 'D'
0x1800378a6  jb      loc_180037A9D
0x1800378ac  mov     [rsp+0C0h+arg_0], rsi
0x1800378b4  mov     edi, 44h ; 'D'
0x1800378b9  mov     rsi, [rbx+18h]
0x1800378bd  mov     [rsp+0C0h+arg_18], r12
0x1800378c5  mov     [rsp+0B0h], r13
0x1800378cd  mov     [rsp+0C0h+var_20], r15
0x1800378d5  mov     r15, [rbx+8]
0x1800378d9  mov     [rsi], rdi
0x1800378dc  movups  xmm0, xmmword ptr [r15]
0x1800378e0  movups  xmmword ptr [rsi+8], xmm0
0x1800378e4  cmp     [r15+278h], r14b
0x1800378eb  jz      loc_180037AB3
0x1800378f1  mov     dword ptr [rsi+4], 1
0x1800378f8  mov     ecx, 3
0x1800378fd  mov     eax, [r15+20h]
0x180037901  mov     [rsi+18h], eax
0x180037904  movups  xmm0, xmmword ptr [r15+24h]
0x180037909  movups  xmmword ptr [rsi+1Ch], xmm0
0x18003790d  cmp     [r15+279h], r14b
0x180037914  jz      loc_180037A32
0x18003791a  mov     [rsi+4], ecx
0x18003791d  movups  xmm0, xmmword ptr [r15+34h]
0x180037922  xor     ecx, ecx; dwErrCode
0x180037924  movups  xmmword ptr [rsi+2Ch], xmm0
0x180037928  call    cs:__imp_SetLastError
0x18003792f  nop     dword ptr [rax+rax+00h]
0x180037934  lea     rax, ?__stc@?1??Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)'::`2'::__stc
0x18003793b  mov     [rbp+57h+var_90], r14d
0x18003793f  mov     [rbp+57h+var_58.Context], rax
0x180037943  lea     rcx, [rbp+57h+var_58]; this
0x180037947  lea     rax, [rbp+57h+var_90]
0x18003794b  mov     [rbp+57h+var_58.Flags], 1
0x180037952  mov     [rbp+57h+var_30], rax
0x180037956  lea     r12, [rsi+3Ch]
0x18003795a  lea     r13, [rsi+40h]
0x18003795e  mov     [rbp+57h+var_58.Previous], r14
0x180037962  mov     [rbp+57h+var_40], 20737853h
0x18003796a  mov     [rbp+57h+var_38], 58Eh
0x180037971  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180037976  test    r13, r13
0x180037979  jz      short loc_18003797F
0x18003797b  mov     [r13+0], r14d
0x18003797f  test    r12, r12
0x180037982  jz      short loc_180037988
0x180037984  mov     [r12], r14d
0x180037988  mov     r14, [r15+68h]
0x18003798c  test    r14, r14
0x18003798f  jz      short loc_1800379B8
0x180037991  mov     rax, [rbp+57h+var_A0]
0x180037995  lea     r14, ds:2[r14*2]
0x18003799d  add     rax, 0FFFFFFFFFFFFFFBCh
0x1800379a1  cmp     rax, r14
0x1800379a4  jb      loc_180037AC0
0x1800379aa  mov     eax, 0FFFFFFFFh
0x1800379af  cmp     r14, rax
0x1800379b2  ja      loc_180037AC0
0x1800379b8  mov     rdx, [r15+58h]; Src
0x1800379bc  lea     rcx, [rsi+44h]; void *
0x1800379c0  mov     r8, r14; Size
0x1800379c3  call    memcpy_0
0x1800379c8  test    r13, r13
0x1800379cb  jnz     loc_180037A64
0x1800379d1  test    r12, r12
0x1800379d4  jnz     short loc_180037A3E
0x1800379d6  lea     rdi, [r14+44h]
0x1800379da  mov     [rbp+57h+var_90], 1
0x1800379e1  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800379e8  mov     esi, [rbp+57h+var_90]
0x1800379eb  mov     r15, [rsp+0C0h+var_20]
0x1800379f3  mov     r13, [rsp+0B0h]
0x1800379fb  mov     r12, [rsp+0C0h+arg_18]
0x180037a03  jnz     loc_180037ADD
0x180037a09  lea     rcx, [rbp+57h+var_58]; Frame
0x180037a0d  call    cs:__imp_RtlPopFrame
0x180037a14  nop     dword ptr [rax+rax+00h]
0x180037a19  test    esi, esi
0x180037a1b  mov     rsi, [rsp+0C0h+arg_0]
0x180037a23  jz      loc_180037B0C
0x180037a29  mov     [rbx+20h], rdi
0x180037a2d  jmp     loc_18003781F
0x180037a32  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180037a39  jmp     loc_180037922
0x180037a3e  test    r14, r14
0x180037a41  jz      short loc_180037A57
0x180037a43  lea     eax, [r14-2]
0x180037a47  mov     [r12], eax
0x180037a4b  jmp     short loc_1800379D6
0x180037a4d  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180037a52  jmp     loc_1800377FC
0x180037a57  mov     dword ptr [r12], 0
0x180037a5f  jmp     loc_1800379D6
0x180037a64  test    r14, r14
0x180037a67  jz      loc_1800379D1
0x180037a6d  mov     [r13+0], edi
0x180037a71  jmp     loc_1800379D1
0x180037a76  cmp     edi, 1
0x180037a79  jnz     loc_18003781F
0x180037a7f  mov     rcx, [rbx]; this
0x180037a82  mov     [rbp+57h+var_A0], r14
0x180037a86  mov     [rbp+57h+var_98], r14b
0x180037a8a  test    rcx, rcx
0x180037a8d  jnz     short loc_180037AD6
0x180037a8f  lea     rcx, [rbp+57h+var_A0]
0x180037a93  call    ??1?$CSmartPtr@U_IID_ENTRY@@V?$CSmartPtrBaseTypeHelper@U_IID_ENTRY@@@@@@QEAA@XZ; CSmartPtr<_IID_ENTRY,CSmartPtrBaseTypeHelper<_IID_ENTRY>>::~CSmartPtr<_IID_ENTRY,CSmartPtrBaseTypeHelper<_IID_ENTRY>>(void)
0x180037a98  jmp     loc_18003781F
0x180037a9d  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180037aa2  call    cs:__imp_SetLastError
0x180037aa9  nop     dword ptr [rax+rax+00h]
0x180037aae  jmp     loc_180037837
0x180037ab3  mov     eax, r14d
0x180037ab6  mov     ecx, 2
0x180037abb  jmp     loc_180037901
0x180037ac0  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180037ac5  call    cs:__imp_SetLastError
0x180037acc  nop     dword ptr [rax+rax+00h]
0x180037ad1  jmp     loc_1800379E1
0x180037ad6  call    ??_G_IID_ENTRY@@QEAAPEAXI@Z; _IID_ENTRY::`scalar deleting destructor'(uint)
0x180037adb  jmp     short loc_180037A8F
0x180037add  mov     rax, [rbp+57h+var_30]
0x180037ae1  cmp     dword ptr [rax], 0
0x180037ae4  jz      short loc_180037AF2
0x180037ae6  xor     ecx, ecx; char *
0x180037ae8  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180037aed  jmp     loc_180037A09
0x180037af2  call    cs:__imp_GetLastError
0x180037af9  nop     dword ptr [rax+rax+00h]
0x180037afe  mov     ecx, eax; unsigned int
0x180037b00  xor     edx, edx; Format
0x180037b02  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180037b07  jmp     loc_180037A09
0x180037b0c  mov     rax, [rbp+57h+var_60]
0x180037b10  lea     rcx, off_18007BA60; struct _CALL_SITE_INFO *
0x180037b17  mov     dword ptr [rax], 0
0x180037b1d  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180037b22  jmp     loc_180037837
0x180037b27  test    ebx, ebx
0x180037b29  jz      short loc_180037B37
0x180037b2b  xor     ecx, ecx; char *
0x180037b2d  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180037b32  jmp     loc_18003785A
0x180037b37  call    cs:__imp_GetLastError
0x180037b3e  nop     dword ptr [rax+rax+00h]
0x180037b43  mov     ecx, eax; unsigned int
0x180037b45  xor     edx, edx; Format
0x180037b47  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180037b4c  jmp     loc_18003785A
```
