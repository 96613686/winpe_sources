# CClsidMap::MapReferenceClsidToConfiguredClsid(_GUID const *,_ACTCTXCTB_ASSEMBLY_CONTEXT const *,_GUID *,_GUID *)

- ea: `0x180046d48`
- end: `0x180046ece`
- name: `?MapReferenceClsidToConfiguredClsid@CClsidMap@@QEAAHPEBU_GUID@@PEBU_ACTCTXCTB_ASSEMBLY_CONTEXT@@PEAU2@2@Z`
- size: `390`
- prototype: `__int64 __fastcall(CClsidMap *__hidden this, const struct _GUID *, const struct _ACTCTXCTB_ASSEMBLY_CONTEXT *, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002a70`
- `0x180045cb0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180046d48`
- `0x180046ed4`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046dd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046dd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046de9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046de9`
- `RPCRT4!UuidCreate` at `0x180046ea5`
- `RPCRT4!UuidCreate` at `0x180046ea5`

## pseudocode

```c
__int64 __fastcall CClsidMap::MapReferenceClsidToConfiguredClsid(
        CClsidMap *this,
        const struct _GUID *a2,
        const struct _ACTCTXCTB_ASSEMBLY_CONTEXT *a3,
        struct _GUID *a4,
        struct _GUID *a5)
{
  unsigned int v6; // edi
  _QWORD *i; // rbx
  struct _GUID v10; // xmm1
  __int64 v12; // rax
  _QWORD *v13; // [rsp+20h] [rbp-50h] BYREF
  char v14; // [rsp+28h] [rbp-48h]
  int v15; // [rsp+30h] [rbp-40h] BYREF
  int v16; // [rsp+38h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-30h]
  __int64 *v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+50h] [rbp-20h]
  int v20; // [rsp+58h] [rbp-18h]
  int *v21; // [rsp+60h] [rbp-10h]

  v18 = &qword_180071510;
  v15 = 0;
  v6 = 1;
  v21 = &v15;
  v16 = 1;
  v17 = 0;
  v19 = 544438355;
  v20 = 63;
  CFrame::BaseEnter((CFrame *)&v16);
  for ( i = (_QWORD *)*((_QWORD *)this + 1); i; i = (_QWORD *)*i )
  {
    v12 = i[1] - *(_QWORD *)&a2->Data1;
    if ( !v12 )
      v12 = i[2] - *(_QWORD *)a2->Data4;
    if ( !v12 )
      goto LABEL_5;
  }
  v14 = 0;
  SetLastError(0);
  v13 = HeapAlloc(g_hHeap, 0, 0x38u);
  i = v13;
  if ( !v13 )
  {
    *v21 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800714F0);
    CSmartArrayPtr<unsigned char>::~CSmartArrayPtr<unsigned char>(&v13);
    v6 = v15;
    goto LABEL_6;
  }
  *v13 = *((_QWORD *)this + 1);
  *(struct _GUID *)(i + 1) = *a2;
  *(struct _GUID *)(i + 5) = *a2;
  UuidCreate((UUID *)(i + 3));
  ++*(_DWORD *)this;
  v13 = 0;
  *((_QWORD *)this + 1) = i;
  CSmartArrayPtr<unsigned char>::~CSmartArrayPtr<unsigned char>(&v13);
LABEL_5:
  *a4 = *(struct _GUID *)(i + 3);
  v10 = *(struct _GUID *)(i + 5);
  v15 = 1;
  *a5 = v10;
LABEL_6:
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v16);
  return v6;
}

```

## disassembly

```asm
0x180046d48  mov     [rsp-28h+arg_8], rbx
0x180046d4d  mov     [rsp-28h+arg_10], rsi
0x180046d52  push    rbp
0x180046d53  push    rdi
0x180046d54  push    r12
0x180046d56  push    r14
0x180046d58  push    r15
0x180046d5a  mov     rbp, rsp
0x180046d5d  sub     rsp, 70h
0x180046d61  mov     rax, cs:__security_cookie
0x180046d68  xor     rax, rsp
0x180046d6b  mov     [rbp+var_8], rax
0x180046d6f  mov     r12, [rbp+arg_20]
0x180046d73  lea     rax, qword_180071510
0x180046d7a  mov     [rbp+var_28], rax
0x180046d7e  mov     r14, rcx
0x180046d81  lea     rax, [rbp+var_40]
0x180046d85  mov     [rbp+var_40], 0
0x180046d8c  mov     edi, 1
0x180046d91  mov     [rbp+var_10], rax
0x180046d95  lea     rcx, [rbp+var_38]; this
0x180046d99  mov     [rbp+var_38], edi
0x180046d9c  mov     r15, r9
0x180046d9f  mov     [rbp+var_30], 0
0x180046da7  mov     rsi, rdx
0x180046daa  mov     [rbp+var_20], 20737853h
0x180046db2  mov     [rbp+var_18], 3Fh ; '?'
0x180046db9  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180046dbe  mov     rbx, [r14+8]
0x180046dc2  test    rbx, rbx
0x180046dc5  jnz     loc_180046E6C
0x180046dcb  xor     ecx, ecx; dwErrCode
0x180046dcd  mov     [rbp+var_48], bl
0x180046dd0  call    cs:__imp_SetLastError
0x180046dd7  nop     dword ptr [rax+rax+00h]
0x180046ddc  mov     rcx, cs:g_hHeap; hHeap
0x180046de3  lea     r8d, [rbx+38h]; dwBytes
0x180046de7  xor     edx, edx; dwFlags
0x180046de9  call    cs:__imp_HeapAlloc
0x180046df0  nop     dword ptr [rax+rax+00h]
0x180046df5  mov     [rbp+var_50], rax
0x180046df9  mov     rbx, rax
0x180046dfc  test    rax, rax
0x180046dff  jnz     loc_180046E8A
0x180046e05  mov     rax, [rbp+var_10]
0x180046e09  lea     rcx, off_1800714F0; struct _CALL_SITE_INFO *
0x180046e10  mov     [rax], ebx
0x180046e12  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180046e17  lea     rcx, [rbp+var_50]
0x180046e1b  call    ??1?$CSmartArrayPtr@E@@QEAA@XZ; CSmartArrayPtr<uchar>::~CSmartArrayPtr<uchar>(void)
0x180046e20  mov     edi, [rbp+var_40]
0x180046e23  jmp     short loc_180046E3B
0x180046e25  movups  xmm0, xmmword ptr [rbx+18h]
0x180046e29  movdqu  xmmword ptr [r15], xmm0
0x180046e2e  movups  xmm1, xmmword ptr [rbx+28h]
0x180046e32  mov     [rbp+var_40], edi
0x180046e35  movdqu  xmmword ptr [r12], xmm1
0x180046e3b  lea     rcx, [rbp+var_38]; this
0x180046e3f  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180046e44  mov     eax, edi
0x180046e46  mov     rcx, [rbp+var_8]
0x180046e4a  xor     rcx, rsp; StackCookie
0x180046e4d  call    __security_check_cookie
0x180046e52  lea     r11, [rsp+70h+var_s0]
0x180046e57  mov     rbx, [r11+38h]
0x180046e5b  mov     rsi, [r11+40h]
0x180046e5f  mov     rsp, r11
0x180046e62  pop     r15
0x180046e64  pop     r14
0x180046e66  pop     r12
0x180046e68  pop     rdi
0x180046e69  pop     rbp
0x180046e6a  retn
0x180046e6c  mov     rax, [rbx+8]
0x180046e70  sub     rax, [rsi]
0x180046e73  jnz     short loc_180046E7D
0x180046e75  mov     rax, [rbx+10h]
0x180046e79  sub     rax, [rsi+8]
0x180046e7d  test    rax, rax
0x180046e80  jz      short loc_180046E25
0x180046e82  mov     rbx, [rbx]
0x180046e85  jmp     loc_180046DC2
0x180046e8a  mov     rax, [r14+8]
0x180046e8e  lea     rcx, [rbx+18h]; Uuid
0x180046e92  mov     [rbx], rax
0x180046e95  movups  xmm0, xmmword ptr [rsi]
0x180046e98  movdqu  xmmword ptr [rbx+8], xmm0
0x180046e9d  movups  xmm1, xmmword ptr [rsi]
0x180046ea0  movdqu  xmmword ptr [rbx+28h], xmm1
0x180046ea5  call    cs:__imp_UuidCreate
0x180046eac  nop     dword ptr [rax+rax+00h]
0x180046eb1  add     [r14], edi
0x180046eb4  lea     rcx, [rbp+var_50]
0x180046eb8  mov     [rbp+var_50], 0
0x180046ec0  mov     [r14+8], rbx
0x180046ec4  call    ??1?$CSmartArrayPtr@E@@QEAA@XZ; CSmartArrayPtr<uchar>::~CSmartArrayPtr<uchar>(void)
0x180046ec9  jmp     loc_180046E25
```
