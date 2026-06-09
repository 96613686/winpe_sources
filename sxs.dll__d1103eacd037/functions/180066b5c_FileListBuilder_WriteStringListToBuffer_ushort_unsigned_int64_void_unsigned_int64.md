# FileListBuilder::WriteStringListToBuffer(ushort *,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x180066b5c`
- end: `0x180066cd4`
- name: `?WriteStringListToBuffer@FileListBuilder@@QEAAHPEAG_KPEAXPEA_K@Z`
- size: `376`
- prototype: `__int64 __fastcall(FileListBuilder *__hidden this, unsigned __int16 *, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800528b0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180037ec4`
- `0x18004a810`
- `0x180066b5c`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c88`

## pseudocode

```c
__int64 __fastcall FileListBuilder::WriteStringListToBuffer(
        FileListBuilder *this,
        unsigned __int16 *a2,
        size_t a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  char *v9; // rdi
  char *i; // rbx
  unsigned int v11; // ebx
  char *v13; // [rsp+40h] [rbp-21h] BYREF
  char *v14; // [rsp+48h] [rbp-19h]
  size_t v15; // [rsp+50h] [rbp-11h] BYREF
  void *v16; // [rsp+58h] [rbp-9h] BYREF
  int v17; // [rsp+60h] [rbp-1h] BYREF
  int v18; // [rsp+68h] [rbp+7h] BYREF
  __int64 v19; // [rsp+70h] [rbp+Fh]
  __int64 *v20; // [rsp+78h] [rbp+17h]
  __int64 v21; // [rsp+80h] [rbp+1Fh]
  int v22; // [rsp+88h] [rbp+27h]
  unsigned int *v23; // [rsp+90h] [rbp+2Fh]

  v17 = 0;
  v20 = &`FileListBuilder::WriteStringListToBuffer'::`2'::__stc;
  v18 = 1;
  v23 = (unsigned int *)&v17;
  v19 = 0;
  v21 = 544438355;
  v22 = 112;
  CFrame::BaseEnter((CFrame *)&v18);
  v16 = a2;
  v13 = (char *)this + 568;
  v15 = a3;
  v14 = 0;
  CConstDequeIterator<_COM_FILE_CONTEXT,0>::Reset(&v13);
  v9 = v13;
  for ( i = v14; i && i != v9; i = *(char **)i )
  {
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                          (__int64)(i + 32),
                          &v16,
                          &v15,
                          a5,
                          a4,
                          (_DWORD *)i + 149,
                          (_DWORD *)i + 148) )
    {
      *v23 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`FileListBuilder::WriteStringListToBuffer'::`17'::__callsite);
      goto LABEL_8;
    }
  }
  SetLastError(0);
  *v23 = 1;
LABEL_8:
  v11 = *v23;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v18);
  return v11;
}

```

## disassembly

```asm
0x180066b5c  mov     [rsp-8+arg_0], rbx
0x180066b61  mov     [rsp-8+arg_10], rsi
0x180066b66  push    rbp
0x180066b67  push    rdi
0x180066b68  push    r14
0x180066b6a  lea     rbp, [rsp-3Fh]
0x180066b6f  sub     rsp, 0A0h
0x180066b76  mov     rax, cs:__security_cookie
0x180066b7d  xor     rax, rsp
0x180066b80  mov     [rbp+4Fh+var_18], rax
0x180066b84  lea     rax, ?__stc@?1??WriteStringListToBuffer@FileListBuilder@@QEAAHPEAG_KPEAXPEA_K@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `FileListBuilder::WriteStringListToBuffer(ushort *,unsigned __int64,void *,unsigned __int64 *)'::`2'::__stc
0x180066b8b  mov     [rbp+4Fh+var_50], 0
0x180066b92  mov     [rbp+4Fh+var_38], rax
0x180066b96  mov     rdi, rcx
0x180066b99  lea     rax, [rbp+4Fh+var_50]
0x180066b9d  mov     [rbp+4Fh+var_48], 1
0x180066ba4  lea     rcx, [rbp+4Fh+var_48]; this
0x180066ba8  mov     [rbp+4Fh+var_20], rax
0x180066bac  mov     r14, r9
0x180066baf  mov     [rbp+4Fh+var_40], 0
0x180066bb7  mov     rsi, r8
0x180066bba  mov     [rbp+4Fh+var_30], 20737853h
0x180066bc2  mov     rbx, rdx
0x180066bc5  mov     [rbp+4Fh+var_28], 70h ; 'p'
0x180066bcc  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180066bd1  lea     rax, [rdi+238h]
0x180066bd8  mov     [rbp+4Fh+var_58], rbx
0x180066bdc  lea     rcx, [rbp+4Fh+var_70]
0x180066be0  mov     [rbp+4Fh+var_70], rax
0x180066be4  mov     [rbp+4Fh+var_60], rsi
0x180066be8  mov     [rbp+4Fh+var_68], 0
0x180066bf0  call    ?Reset@?$CConstDequeIterator@U_COM_FILE_CONTEXT@@$0A@@@QEAAXXZ; CConstDequeIterator<_COM_FILE_CONTEXT,0>::Reset(void)
0x180066bf5  mov     rdi, [rbp+4Fh+var_70]
0x180066bf9  mov     rbx, [rbp+4Fh+var_68]
0x180066bfd  test    rbx, rbx
0x180066c00  jz      loc_180066C86
0x180066c06  cmp     rbx, rdi
0x180066c09  jz      short loc_180066C86
0x180066c0b  xor     ecx, ecx; dwErrCode
0x180066c0d  call    cs:__imp_SetLastError
0x180066c14  nop     dword ptr [rax+rax+00h]
0x180066c19  mov     r9, [rbp+4Fh+arg_20]
0x180066c1d  xor     eax, eax
0x180066c1f  cmp     rbx, rdi
0x180066c22  mov     rcx, rbx
0x180066c25  mov     r8, rbx
0x180066c28  mov     rdx, rbx
0x180066c2b  cmovz   r8, rax
0x180066c2f  cmovz   rcx, rax
0x180066c33  cmovz   rdx, rax
0x180066c37  add     rdx, 254h
0x180066c3e  lea     rax, [rcx+250h]
0x180066c45  mov     [rsp+0B0h+var_80], rax
0x180066c4a  lea     rcx, [r8+20h]
0x180066c4e  mov     [rsp+0B0h+var_88], rdx
0x180066c53  lea     r8, [rbp+4Fh+var_60]
0x180066c57  lea     rdx, [rbp+4Fh+var_58]
0x180066c5b  mov     [rsp+0B0h+var_90], r14
0x180066c60  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x180066c65  test    eax, eax
0x180066c67  jz      short loc_180066C6E
0x180066c69  mov     rbx, [rbx]
0x180066c6c  jmp     short loc_180066BFD
0x180066c6e  mov     rax, [rbp+4Fh+var_20]
0x180066c72  lea     rcx, ?__callsite@?BB@??WriteStringListToBuffer@FileListBuilder@@QEAAHPEAG_KPEAXPEA_K@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180066c79  mov     dword ptr [rax], 0
0x180066c7f  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180066c84  jmp     short loc_180066C9E
0x180066c86  xor     ecx, ecx; dwErrCode
0x180066c88  call    cs:__imp_SetLastError
0x180066c8f  nop     dword ptr [rax+rax+00h]
0x180066c94  mov     rax, [rbp+4Fh+var_20]
0x180066c98  mov     dword ptr [rax], 1
0x180066c9e  mov     rax, [rbp+4Fh+var_20]
0x180066ca2  lea     rcx, [rbp+4Fh+var_48]; this
0x180066ca6  mov     ebx, [rax]
0x180066ca8  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180066cad  mov     eax, ebx
0x180066caf  mov     rcx, [rbp+4Fh+var_18]
0x180066cb3  xor     rcx, rsp; StackCookie
0x180066cb6  call    __security_check_cookie
0x180066cbb  lea     r11, [rsp+0B0h+var_10]
0x180066cc3  mov     rbx, [r11+20h]
0x180066cc7  mov     rsi, [r11+30h]
0x180066ccb  mov     rsp, r11
0x180066cce  pop     r14
0x180066cd0  pop     rdi
0x180066cd1  pop     rbp
0x180066cd2  retn
```
