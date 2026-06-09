# SxspComTypeLibRedirectionGuidSectionGenerationCallback(void *,ulong,void *)

- ea: `0x180049970`
- end: `0x180049cec`
- name: `?SxspComTypeLibRedirectionGuidSectionGenerationCallback@@YAHPEAXK0@Z`
- size: `892`
- prototype: `__int64 __fastcall(CDequeBase *this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180037ec4`
- `0x1800498cc`
- `0x180049970`
- `0x180049cf4`
- `0x18004a810`
- `0x180056760`
- `0x180066988`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180049a22`
- `ntdll!RtlPopFrame` at `0x180049a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049aa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049b4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049bc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049bd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049c28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049aa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049b4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049bc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049bd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049c28`

## pseudocode

```c
__int64 __fastcall SxspComTypeLibRedirectionGuidSectionGenerationCallback(CDequeBase *this, int a2, __int64 *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  CDequeBase *i; // rcx
  unsigned int v12; // ebx
  struct CDequeLinkage *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  _TLB_ENTRY *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // rcx
  char **v23; // rcx
  CDequeBase *v24; // rdi
  CDequeBase *j; // rbx
  _TLB_FILE_CONTEXT *v26; // rcx
  DWORD LastError; // eax
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  CDequeBase *v31; // [rsp+58h] [rbp-11h] BYREF
  CDequeBase *v32; // [rsp+60h] [rbp-9h]
  int v33; // [rsp+68h] [rbp-1h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+70h] [rbp+7h] BYREF
  __int64 v35; // [rsp+88h] [rbp+1Fh]
  int v36; // [rsp+90h] [rbp+27h]
  int *v37; // [rsp+98h] [rbp+2Fh]

  v33 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800718B0;
  Frame.Flags = 1;
  v37 = &v33;
  Frame.Previous = 0;
  v35 = 544438355;
  v36 = 426;
  CFrame::BaseEnter((CFrame *)&Frame);
  v7 = a2 - 1;
  if ( !v7 )
  {
    v14 = (struct CDequeLinkage *)*a3;
    v15 = 32;
    a3[1] = 32;
    if ( v14 )
    {
      v16 = *((_QWORD *)v14 + 11);
      if ( v16 )
        v15 = 2 * v16 + 34;
      a3[1] = v15;
    }
    goto LABEL_7;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v17 = a3[2];
    if ( v17 < 0x20 )
    {
      SetLastError(0x7Au);
      goto LABEL_8;
    }
    v20 = a3[1];
    v21 = a3[3];
    v30 = v17 - 32;
    v28 = 32;
    v22 = *(_QWORD *)(v20 + 32);
    *(_QWORD *)v21 = 32;
    v29 = v21 + 32;
    *(_DWORD *)(v21 + 8) = 2 * *(_DWORD *)(v22 + 104) + 2;
    *(_DWORD *)(v21 + 12) = *(_DWORD *)(v22 + 632);
    *(_WORD *)(v21 + 16) = *(_WORD *)(v20 + 620);
    *(_WORD *)(v21 + 18) = *(_WORD *)(v20 + 622);
    *(_DWORD *)(v21 + 28) = *(_DWORD *)(v20 + 616);
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                         v20 + 56,
                         (void **)&v29,
                         &v30,
                         &v28,
                         v21,
                         (_DWORD *)(v21 + 24),
                         (_DWORD *)(v21 + 20)) )
    {
      a3[4] = v28;
LABEL_7:
      v33 = 1;
      goto LABEL_8;
    }
    v23 = off_180071970;
    goto LABEL_24;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v18 = (_TLB_ENTRY *)*a3;
    if ( *a3 )
    {
      v19 = *((_QWORD *)v18 + 4);
      if ( v19 )
      {
        CDeque<_TLB_ENTRY,0>::Remove((CDequeBase *)(v19 + 32), (struct CDequeLinkage *)*a3);
        v6 = *((_QWORD *)v18 + 4);
        if ( !*(_QWORD *)(v6 + 64) )
        {
          CDeque<_TLB_FILE_CONTEXT,0>::Remove(this, (struct CDequeLinkage *)v6);
          v26 = (_TLB_FILE_CONTEXT *)*((_QWORD *)v18 + 4);
          if ( v26 )
            _TLB_FILE_CONTEXT::`scalar deleting destructor'(v26, v6);
        }
      }
      _TLB_ENTRY::`scalar deleting destructor'(v18, v6);
    }
    goto LABEL_7;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    for ( i = *(CDequeBase **)this; i && i != this; i = *(CDequeBase **)i )
      *a3 += 2LL * *((_QWORD *)i + 13) + 2;
    goto LABEL_7;
  }
  if ( v10 == 1 )
  {
    v29 = a3[1];
    v30 = a3[2];
    v28 = 0;
    v31 = this;
    v32 = 0;
    CConstDequeIterator<_COM_FILE_CONTEXT,0>::Reset(&v31);
    v24 = v31;
    for ( j = v32; ; j = *(CDequeBase **)j )
    {
      if ( !j || j == v24 )
      {
        a3[3] = v28;
        goto LABEL_7;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                            (__int64)j + 72,
                            (void **)&v30,
                            (size_t *)&v29,
                            &v28,
                            *a3,
                            (_DWORD *)j + 158,
                            0) )
        break;
    }
    v23 = off_18007B840;
LABEL_24:
    *v37 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v23);
    goto LABEL_8;
  }
  SetLastError(0);
  SetLastError(0);
  *v37 = 1;
LABEL_8:
  v12 = v33;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v37 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v12;
}

```

## disassembly

```asm
0x180049970  mov     [rsp-8+arg_8], rbx
0x180049975  push    rbp
0x180049976  push    rsi
0x180049977  push    rdi
0x180049978  lea     rbp, [rsp-47h]
0x18004997d  sub     rsp, 0B0h
0x180049984  mov     rax, cs:__security_cookie
0x18004998b  xor     rax, rsp
0x18004998e  mov     [rbp+57h+var_20], rax
0x180049992  lea     rax, qword_1800718B0
0x180049999  mov     [rbp+57h+var_58], 0
0x1800499a0  mov     [rbp+57h+Frame.Context], rax
0x1800499a4  mov     rdi, rcx
0x1800499a7  lea     rax, [rbp+57h+var_58]
0x1800499ab  mov     [rbp+57h+Frame.Flags], 1
0x1800499b2  lea     rcx, [rbp+57h+Frame]; this
0x1800499b6  mov     [rbp+57h+var_28], rax
0x1800499ba  mov     rsi, r8
0x1800499bd  mov     [rbp+57h+Frame.Previous], 0
0x1800499c5  mov     ebx, edx
0x1800499c7  mov     [rbp+57h+var_38], 20737853h
0x1800499cf  mov     [rbp+57h+var_30], 1AAh
0x1800499d6  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800499db  sub     ebx, 1
0x1800499de  jz      loc_180049A69
0x1800499e4  sub     ebx, 1
0x1800499e7  jz      loc_180049A94
0x1800499ed  sub     ebx, 1
0x1800499f0  jz      loc_180049AB6
0x1800499f6  sub     ebx, 1
0x1800499f9  jnz     loc_180049BBF
0x1800499ff  mov     rcx, [rdi]
0x180049a02  test    rcx, rcx
0x180049a05  jnz     short loc_180049A50
0x180049a07  mov     [rbp+57h+var_58], 1
0x180049a0e  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180049a15  mov     ebx, [rbp+57h+var_58]
0x180049a18  jnz     loc_180049CBD
0x180049a1e  lea     rcx, [rbp+57h+Frame]; Frame
0x180049a22  call    cs:__imp_RtlPopFrame
0x180049a29  nop     dword ptr [rax+rax+00h]
0x180049a2e  mov     eax, ebx
0x180049a30  mov     rcx, [rbp+57h+var_20]
0x180049a34  xor     rcx, rsp; StackCookie
0x180049a37  call    __security_check_cookie
0x180049a3c  mov     rbx, [rsp+0C0h+arg_8]
0x180049a44  add     rsp, 0B0h
0x180049a4b  pop     rdi
0x180049a4c  pop     rsi
0x180049a4d  pop     rbp
0x180049a4e  retn
0x180049a50  cmp     rcx, rdi
0x180049a53  jz      short loc_180049A07
0x180049a55  mov     rax, [rcx+68h]
0x180049a59  lea     rax, ds:2[rax*2]
0x180049a61  add     [rsi], rax
0x180049a64  mov     rcx, [rcx]
0x180049a67  jmp     short loc_180049A02
0x180049a69  mov     rax, [rsi]
0x180049a6c  mov     edx, 20h ; ' '
0x180049a71  mov     [rsi+8], rdx
0x180049a75  test    rax, rax
0x180049a78  jz      short loc_180049A07
0x180049a7a  mov     rax, [rax+58h]
0x180049a7e  test    rax, rax
0x180049a81  jz      short loc_180049A8B
0x180049a83  lea     rdx, ds:22h[rax*2]
0x180049a8b  mov     [rsi+8], rdx
0x180049a8f  jmp     loc_180049A07
0x180049a94  mov     rax, [rsi+10h]
0x180049a98  mov     edx, 20h ; ' '
0x180049a9d  cmp     rax, rdx
0x180049aa0  jnb     short loc_180049AF3
0x180049aa2  lea     ecx, [rdx+5Ah]; dwErrCode
0x180049aa5  call    cs:__imp_SetLastError
0x180049aac  nop     dword ptr [rax+rax+00h]
0x180049ab1  jmp     loc_180049A0E
0x180049ab6  mov     rbx, [rsi]
0x180049ab9  test    rbx, rbx
0x180049abc  jz      loc_180049A07
0x180049ac2  mov     rcx, [rbx+20h]
0x180049ac6  test    rcx, rcx
0x180049ac9  jz      short loc_180049AE6
0x180049acb  add     rcx, 20h ; ' '; this
0x180049acf  mov     rdx, rbx; struct CDequeLinkage *
0x180049ad2  call    ?Remove@?$CDeque@U_TLB_ENTRY@@$0A@@@QEAAXPEAU_TLB_ENTRY@@@Z; CDeque<_TLB_ENTRY,0>::Remove(_TLB_ENTRY *)
0x180049ad7  mov     rdx, [rbx+20h]; struct CDequeLinkage *
0x180049adb  cmp     qword ptr [rdx+40h], 0
0x180049ae0  jz      loc_180049C91
0x180049ae6  mov     rcx, rbx; this
0x180049ae9  call    ??_G_TLB_ENTRY@@QEAAPEAXI@Z; _TLB_ENTRY::`scalar deleting destructor'(uint)
0x180049aee  jmp     loc_180049A07
0x180049af3  mov     rbx, [rsi+8]
0x180049af7  add     rax, 0FFFFFFFFFFFFFFE0h
0x180049afb  mov     rdi, [rsi+18h]
0x180049aff  mov     [rbp+57h+var_70], rax
0x180049b03  mov     [rbp+57h+var_80], rdx
0x180049b07  mov     rcx, [rbx+20h]
0x180049b0b  mov     [rdi], rdx
0x180049b0e  lea     rax, [rdi+20h]
0x180049b12  mov     [rbp+57h+var_78], rax
0x180049b16  mov     eax, [rcx+68h]
0x180049b19  lea     eax, ds:2[rax*2]
0x180049b20  mov     [rdi+8], eax
0x180049b23  mov     eax, [rcx+278h]
0x180049b29  xor     ecx, ecx; dwErrCode
0x180049b2b  mov     [rdi+0Ch], eax
0x180049b2e  movzx   eax, word ptr [rbx+26Ch]
0x180049b35  mov     [rdi+10h], ax
0x180049b39  movzx   eax, word ptr [rbx+26Eh]
0x180049b40  mov     [rdi+12h], ax
0x180049b44  mov     eax, [rbx+268h]
0x180049b4a  mov     [rdi+1Ch], eax
0x180049b4d  call    cs:__imp_SetLastError
0x180049b54  nop     dword ptr [rax+rax+00h]
0x180049b59  lea     rax, [rdi+14h]
0x180049b5d  mov     [rsp+0C0h+var_90], rax
0x180049b62  lea     rdx, [rdi+18h]
0x180049b66  mov     [rsp+0C0h+var_98], rdx
0x180049b6b  lea     rcx, [rbx+38h]
0x180049b6f  lea     rdx, [rbp+57h+var_78]
0x180049b73  mov     [rsp+0C0h+var_A0], rdi
0x180049b78  lea     r9, [rbp+57h+var_80]
0x180049b7c  lea     r8, [rbp+57h+var_70]
0x180049b80  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x180049b85  test    eax, eax
0x180049b87  jnz     loc_180049CB0
0x180049b8d  lea     rcx, off_180071970; struct _CALL_SITE_INFO *
0x180049b94  mov     rax, [rbp+57h+var_28]
0x180049b98  mov     dword ptr [rax], 0
0x180049b9e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180049ba3  jmp     loc_180049A0E
0x180049ba8  test    rbx, rbx
0x180049bab  jz      short loc_180049BB2
0x180049bad  cmp     rbx, rdi
0x180049bb0  jnz     short loc_180049C26
0x180049bb2  mov     rax, [rbp+57h+var_80]
0x180049bb6  mov     [rsi+18h], rax
0x180049bba  jmp     loc_180049A07
0x180049bbf  cmp     ebx, 1
0x180049bc2  jz      short loc_180049BEF
0x180049bc4  xor     ecx, ecx; dwErrCode
0x180049bc6  call    cs:__imp_SetLastError
0x180049bcd  nop     dword ptr [rax+rax+00h]
0x180049bd2  xor     ecx, ecx; dwErrCode
0x180049bd4  call    cs:__imp_SetLastError
0x180049bdb  nop     dword ptr [rax+rax+00h]
0x180049be0  mov     rax, [rbp+57h+var_28]
0x180049be4  mov     dword ptr [rax], 1
0x180049bea  jmp     loc_180049A0E
0x180049bef  mov     rax, [rsi+8]
0x180049bf3  lea     rcx, [rbp+57h+var_68]
0x180049bf7  mov     [rbp+57h+var_78], rax
0x180049bfb  mov     rax, [rsi+10h]
0x180049bff  mov     [rbp+57h+var_70], rax
0x180049c03  mov     [rbp+57h+var_80], 0
0x180049c0b  mov     [rbp+57h+var_68], rdi
0x180049c0f  mov     [rbp+57h+var_60], 0
0x180049c17  call    ?Reset@?$CConstDequeIterator@U_COM_FILE_CONTEXT@@$0A@@@QEAAXXZ; CConstDequeIterator<_COM_FILE_CONTEXT,0>::Reset(void)
0x180049c1c  mov     rdi, [rbp+57h+var_68]
0x180049c20  mov     rbx, [rbp+57h+var_60]
0x180049c24  jmp     short loc_180049BA8
0x180049c26  xor     ecx, ecx; dwErrCode
0x180049c28  call    cs:__imp_SetLastError
0x180049c2f  nop     dword ptr [rax+rax+00h]
0x180049c34  xor     eax, eax
0x180049c36  mov     [rsp+0C0h+var_90], 0
0x180049c3f  cmp     rbx, rdi
0x180049c42  lea     r9, [rbp+57h+var_80]
0x180049c46  mov     rcx, rbx
0x180049c49  lea     r8, [rbp+57h+var_78]
0x180049c4d  cmovz   rcx, rax
0x180049c51  mov     rdx, rbx
0x180049c54  cmovz   rdx, rax
0x180049c58  lea     rax, [rcx+278h]
0x180049c5f  mov     [rsp+0C0h+var_98], rax
0x180049c64  lea     rcx, [rdx+48h]
0x180049c68  mov     rax, [rsi]
0x180049c6b  lea     rdx, [rbp+57h+var_70]
0x180049c6f  mov     [rsp+0C0h+var_A0], rax
0x180049c74  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x180049c79  test    eax, eax
0x180049c7b  jz      short loc_180049C85
0x180049c7d  mov     rbx, [rbx]
0x180049c80  jmp     loc_180049BA8
0x180049c85  lea     rcx, off_18007B840; "clientcore\\base\\win32\\fusion\\sxs\\c"...
0x180049c8c  jmp     loc_180049B94
0x180049c91  mov     rcx, rdi; this
0x180049c94  call    ?Remove@?$CDeque@U_TLB_FILE_CONTEXT@@$0A@@@QEAAXPEAU_TLB_FILE_CONTEXT@@@Z; CDeque<_TLB_FILE_CONTEXT,0>::Remove(_TLB_FILE_CONTEXT *)
0x180049c99  mov     rcx, [rbx+20h]; this
0x180049c9d  test    rcx, rcx
0x180049ca0  jz      loc_180049AE6
0x180049ca6  call    ??_G_TLB_FILE_CONTEXT@@QEAAPEAXI@Z; _TLB_FILE_CONTEXT::`scalar deleting destructor'(uint)
0x180049cab  jmp     loc_180049AE6
0x180049cb0  mov     rax, [rbp+57h+var_80]
0x180049cb4  mov     [rsi+20h], rax
0x180049cb8  jmp     loc_180049A07
0x180049cbd  mov     rax, [rbp+57h+var_28]
0x180049cc1  cmp     dword ptr [rax], 0
0x180049cc4  jz      short loc_180049CD2
0x180049cc6  xor     ecx, ecx; char *
0x180049cc8  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180049ccd  jmp     loc_180049A1E
0x180049cd2  call    cs:__imp_GetLastError
0x180049cd9  nop     dword ptr [rax+rax+00h]
0x180049cde  mov     ecx, eax; unsigned int
0x180049ce0  xor     edx, edx; Format
0x180049ce2  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180049ce7  jmp     loc_180049A1E
```
