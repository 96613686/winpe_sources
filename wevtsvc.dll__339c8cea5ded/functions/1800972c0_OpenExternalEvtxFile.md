# OpenExternalEvtxFile

- ea: `0x1800972c0`
- end: `0x1800974ad`
- name: `OpenExternalEvtxFile`
- size: `493`
- prototype: `_QWORD *__fastcall(_QWORD *, const wchar_t **, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800762f8`
- `0x18008e22c`

## callees

- `0x180016250`
- `0x180047194`
- `0x1800613d8`
- `0x180087370`
- `0x180092008`
- `0x1800972c0`
- `0x1800d334c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800972e5`
- `RPCRT4!RpcImpersonateClient` at `0x1800972e5`
- `RPCRT4!RpcRevertToSelf` at `0x18009748c`
- `RPCRT4!RpcRevertToSelf` at `0x18009748c`

## pseudocode

```c
_QWORD *__fastcall OpenExternalEvtxFile(_QWORD *a1, const wchar_t **a2, char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  void *v8; // rax
  __int64 v9; // rcx
  __int64 v11; // [rsp+38h] [rbp-11h] BYREF
  __int128 v12; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+50h] [rbp+7h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp+17h] BYREF
  __int64 v15; // [rsp+70h] [rbp+27h]
  int v16; // [rsp+78h] [rbp+2Fh]
  __int64 v17; // [rsp+7Ch] [rbp+33h]
  char v18; // [rsp+84h] [rbp+3Bh]

  v6 = RpcImpersonateClient(0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v6);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v15 = 0;
    v16 = v7;
    v17 = -1;
    v18 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !FileExists(*a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 2);
    }
    pExceptionObject = 0;
    v15 = 0;
    v16 = 2;
    v17 = 0x33BFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v12 = 0;
  v13 = *(_OWORD *)a2;
  FileManager::GetFile(
    (_DWORD)g_service + 24,
    (unsigned int)&v11,
    (unsigned int)&v13,
    0,
    (16 * (a3 ^ 1)) | 4,
    (__int64)&v12);
  v8 = operator new(0x18u);
  if ( v8 )
  {
    *(_QWORD *)v8 = &wmi::RefBase::`vftable';
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ExternalEvtxFile::`vftable';
    v9 = v11;
    *((_QWORD *)v8 + 2) = v11;
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 808));
    *a1 = v8;
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  }
  else
  {
    *a1 = 0;
  }
  wmi::AutoRef<File>::Release(&v11);
  RpcRevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x1800972c0  mov     [rsp-8+arg_0], rbx
0x1800972c5  mov     [rsp-8+arg_8], rsi
0x1800972ca  push    rbp
0x1800972cb  push    rdi
0x1800972cc  push    r14
0x1800972ce  lea     rbp, [rsp-47h]
0x1800972d3  sub     rsp, 90h
0x1800972da  mov     sil, r8b
0x1800972dd  mov     r14, rdx
0x1800972e0  mov     rbx, rcx
0x1800972e3  xor     ecx, ecx; BindingHandle
0x1800972e5  call    cs:__imp_RpcImpersonateClient
0x1800972eb  mov     edi, eax
0x1800972ed  test    eax, eax
0x1800972ef  jz      short loc_180097363
0x1800972f1  lea     rdx, WPP_GLOBAL_Control
0x1800972f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800972ff  cmp     rcx, rdx
0x180097302  jz      short loc_180097328
0x180097304  test    byte ptr [rcx+1Ch], 8
0x180097308  jz      short loc_180097328
0x18009730a  cmp     byte ptr [rcx+19h], 2
0x18009730e  jb      short loc_180097328
0x180097310  mov     edx, 31h ; '1'
0x180097315  mov     r9d, eax
0x180097318  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x18009731f  mov     rcx, [rcx+10h]
0x180097323  call    WPP_SF_d
0x180097328  lea     rax, byte_1800EC961
0x18009732f  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180097333  mov     qword ptr [rbp+57h+pExceptionObject+8], 0
0x18009733b  mov     [rbp+57h+var_30], 0
0x180097343  mov     [rbp+57h+var_28], edi
0x180097346  mov     [rbp+57h+var_24], 0FFFFFFFFFFFFFFFFh
0x18009734e  mov     [rbp+57h+var_1C], 0
0x180097352  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180097359  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18009735d  call    _CxxThrowException_0
0x180097363  mov     [rbp+57h+arg_19], 1
0x18009736a  mov     rcx, [r14]; wchar_t *
0x18009736d  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x180097372  test    al, al
0x180097374  jnz     short loc_1800973E4
0x180097376  lea     rdx, WPP_GLOBAL_Control
0x18009737d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097384  cmp     rcx, rdx
0x180097387  jz      short loc_1800973AE
0x180097389  test    byte ptr [rcx+1Ch], 8
0x18009738d  jz      short loc_1800973AE
0x18009738f  cmp     byte ptr [rcx+19h], 2
0x180097393  jb      short loc_1800973AE
0x180097395  mov     edx, 32h ; '2'
0x18009739a  lea     r9d, [rdx-30h]
0x18009739e  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800973a5  mov     rcx, [rcx+10h]
0x1800973a9  call    WPP_SF_d
0x1800973ae  xorps   xmm0, xmm0
0x1800973b1  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800973b6  mov     [rbp+57h+var_30], 0
0x1800973be  mov     [rbp+57h+var_28], 2
0x1800973c5  mov     dword ptr [rbp+57h+var_24], 0FFFFFFFFh
0x1800973cc  mov     dword ptr [rbp+57h+var_24+4], 33Bh
0x1800973d3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800973da  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800973de  call    _CxxThrowException_0
0x1800973e4  xorps   xmm0, xmm0
0x1800973e7  movdqa  [rbp+57h+var_60], xmm0
0x1800973ec  movaps  xmm1, xmmword ptr [r14]
0x1800973f0  movdqa  [rbp+57h+var_50], xmm1
0x1800973f5  xor     sil, 1
0x1800973f9  shl     sil, 4
0x1800973fd  or      sil, 4
0x180097401  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180097408  add     rcx, 18h
0x18009740c  lea     rax, [rbp+57h+var_60]
0x180097410  mov     [rsp+0A0h+var_78], rax
0x180097415  mov     [rsp+0A0h+var_80], sil
0x18009741a  xor     r9d, r9d
0x18009741d  lea     r8, [rbp+57h+var_50]
0x180097421  lea     rdx, [rbp+57h+var_68]
0x180097425  call    ?GetFile@FileManager@@QEAA?AV?$AutoRef@VFile@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_KW4FileModeFlags@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; FileManager::GetFile(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64,FileModeFlags,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18009742a  nop
0x18009742b  mov     ecx, 18h; dwBytes
0x180097430  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180097435  mov     [rbp+7Fh], rax
0x180097439  test    rax, rax
0x18009743c  jz      short loc_18009747B
0x18009743e  lea     rcx, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180097445  mov     [rax], rcx
0x180097448  mov     dword ptr [rax+8], 0
0x18009744f  lea     rcx, ??_7ExternalEvtxFile@@6B@; const ExternalEvtxFile::`vftable'
0x180097456  mov     [rax], rcx
0x180097459  mov     rcx, [rbp+57h+var_68]
0x18009745d  mov     [rax+10h], rcx
0x180097461  test    rcx, rcx
0x180097464  jz      short loc_18009746D
0x180097466  lock inc dword ptr [rcx+328h]
0x18009746d  mov     [rbx], rax
0x180097470  test    rax, rax
0x180097473  jz      short loc_180097482
0x180097475  lock inc dword ptr [rax+8]
0x180097479  jmp     short loc_180097482
0x18009747b  mov     qword ptr [rbx], 0
0x180097482  lea     rcx, [rbp+57h+var_68]
0x180097486  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x18009748b  nop
0x18009748c  call    cs:__imp_RpcRevertToSelf
0x180097492  mov     rax, rbx
0x180097495  lea     r11, [rsp+0A0h+var_10]
0x18009749d  mov     rbx, [r11+20h]
0x1800974a1  mov     rsi, [r11+28h]
0x1800974a5  mov     rsp, r11
0x1800974a8  pop     r14
0x1800974aa  pop     rdi
0x1800974ab  pop     rbp
0x1800974ac  retn
```
