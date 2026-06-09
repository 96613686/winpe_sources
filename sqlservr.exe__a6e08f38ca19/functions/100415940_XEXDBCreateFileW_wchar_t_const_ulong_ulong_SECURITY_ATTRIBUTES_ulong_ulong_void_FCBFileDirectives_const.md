# XEXDBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,FCBFileDirectives const *)

- ea: `0x100415940`
- end: `0x100415b57`
- name: `?XEXDBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z`
- size: `535`
- prototype: `void *__fastcall(const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *, const struct FCBFileDirectives *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x100401580`
- `0x100415940`

## import_xrefs

- `KERNEL32!SetLastError` at `0x100415ad2`
- `KERNEL32!SetLastError` at `0x100415ad2`
- `sqlmin!?IsShuttingDown@DBTABLE@@QEBA_NXZ` at `0x100415ac1`
- `sqlmin!?IsShuttingDown@DBTABLE@@QEBA_NXZ` at `0x100415ac1`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x100415ab3`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x100415ab3`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x100415b28`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x100415b28`

## pseudocode

```c
__int64 __fastcall XEXDBCreateFileW(
        const wchar_t *a1,
        unsigned int a2,
        unsigned int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        unsigned int a5,
        unsigned int a6,
        void *a7,
        const struct FCBFileDirectives *a8)
{
  void *v10; // rdx
  char v13; // bl
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __m128i v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  DBTABLE *v25; // rax
  int v26; // eax
  __int128 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __m128i si128; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]
  __int128 v40; // [rsp+110h] [rbp+10h]

  v29 = 0;
  v10 = a7;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28) = -1;
  v39 = 0;
  v13 = 1;
  DWORD1(v28) = 0x7FFFFFFF;
  *((_QWORD *)&v28 + 1) = 0;
  *((_QWORD *)&v30 + 1) = 0;
  v31 = 0;
  *(_QWORD *)&v32 = 0;
  BYTE8(v32) = 0;
  HIDWORD(v32) = 0;
  LOBYTE(v34) = 0;
  *((_QWORD *)&v34 + 1) = 0;
  LOBYTE(v35) = 0;
  LODWORD(v36) = 0;
  *((_QWORD *)&v36 + 1) = 0;
  LOWORD(v38) = 0;
  DWORD1(v38) = 0;
  BYTE8(v38) = 0;
  *(_QWORD *)&v40 = 0xFFFFFFFF00000000uLL;
  WORD4(v40) = 0;
  BYTE10(v40) = 0;
  v33 = xmmword_10045A6A8;
  if ( a8 )
  {
    v14 = *((_OWORD *)a8 + 1);
    v28 = *(_OWORD *)a8;
    v15 = *((_OWORD *)a8 + 2);
    v29 = v14;
    v16 = *((_OWORD *)a8 + 3);
    v30 = v15;
    v17 = *((_OWORD *)a8 + 4);
    v31 = v16;
    v18 = *((_OWORD *)a8 + 5);
    v32 = v17;
    v19 = *((_OWORD *)a8 + 6);
    v33 = v18;
    v20 = *((_OWORD *)a8 + 8);
    v34 = v19;
    v35 = *((_OWORD *)a8 + 7);
    v21 = *((__m128i *)a8 + 9);
    v36 = v20;
    v22 = *((_OWORD *)a8 + 10);
    si128 = v21;
    v23 = *((_OWORD *)a8 + 11);
    v38 = v22;
    v24 = *((_OWORD *)a8 + 12);
    v39 = v23;
    v40 = v24;
    v25 = DBMgr::LookupDB(*((DBMgr **)qword_10049F360 + 4), (unsigned __int16)v28);
    if ( v25 && DBTABLE::IsShuttingDown(v25) )
    {
      v13 = 0;
      SetLastError(0x139Fu);
    }
    v10 = a7;
  }
  else
  {
    *((_QWORD *)&v35 + 1) = 0x100000001LL;
  }
  v26 = DWORD1(v28);
  if ( (a2 & 0x40000000) != 0 )
    v26 = dword_1004A0A18;
  DWORD1(v28) = v26;
  if ( v13 )
    return (__int64)DBCreateFileW(a1, a2, a3, a4, a5, a6, v10, (const struct FCBFileDirectives *)&v28);
  else
    return -1;
}

```

## disassembly

```asm
0x100415940  push    rbp
0x100415942  push    rbx
0x100415943  push    rsi
0x100415944  push    rdi
0x100415945  push    r12
0x100415947  push    r13
0x100415949  push    r14
0x10041594b  push    r15
0x10041594d  lea     rbp, [rsp-38h]
0x100415952  sub     rsp, 138h
0x100415959  mov     rax, cs:__security_cookie
0x100415960  xor     rax, rsp
0x100415963  mov     [rbp+70h+var_50], rax
0x100415967  mov     r12d, [rbp+70h+arg_20]
0x10041596e  xorps   xmm0, xmm0
0x100415971  mov     r13d, [rbp+70h+arg_28]
0x100415978  mov     eax, 0FFFFh
0x10041597d  movdqa  [rsp+170h+var_110], xmm0
0x100415983  mov     rsi, rcx
0x100415986  movdqa  xmm0, cs:__xmm@00000003000000040000000100000000
0x10041598e  mov     edi, edx
0x100415990  mov     rcx, [rbp+70h+arg_38]
0x100415997  xorps   xmm1, xmm1
0x10041599a  mov     rdx, [rbp+70h+arg_30]
0x1004159a1  mov     r15, r9
0x1004159a4  movdqa  [rbp+70h+var_90], xmm0
0x1004159a9  mov     r14d, r8d
0x1004159ac  xorps   xmm0, xmm0
0x1004159af  mov     [rsp+170h+var_120], ax
0x1004159b4  xor     eax, eax
0x1004159b6  movdqa  [rbp+70h+var_70], xmm0
0x1004159bb  mov     [rsp+170h+var_130], rdx
0x1004159c0  mov     bl, 1
0x1004159c2  mov     [rsp+170h+var_11C], 7FFFFFFFh
0x1004159ca  mov     [rsp+170h+var_118], rax
0x1004159cf  mov     [rsp+170h+var_F8], rax
0x1004159d4  movdqa  [rbp+70h+var_F0], xmm1
0x1004159d9  mov     [rbp+70h+var_E0], rax
0x1004159dd  mov     [rbp+70h+var_D8], al
0x1004159e0  mov     [rbp+70h+var_D4], eax
0x1004159e3  mov     [rbp+70h+var_C0], al
0x1004159e6  mov     [rbp+70h+var_B8], rax
0x1004159ea  mov     [rbp+70h+var_B0], al
0x1004159ed  mov     [rbp+70h+var_A0], eax
0x1004159f0  mov     [rbp+70h+var_98], rax
0x1004159f4  mov     [rbp+70h+var_80], ax
0x1004159f8  mov     [rbp+70h+var_7C], eax
0x1004159fb  mov     [rbp+70h+var_78], al
0x1004159fe  mov     [rbp+70h+var_60], eax
0x100415a01  mov     [rbp+70h+var_5C], 0FFFFFFFFh
0x100415a08  mov     [rbp+70h+var_58], ax
0x100415a0c  mov     [rbp+70h+var_56], al
0x100415a0f  movups  xmm0, cs:xmmword_10045A6A8
0x100415a16  movaps  [rbp+70h+var_D0], xmm0
0x100415a1a  test    rcx, rcx
0x100415a1d  jz      loc_100415ADF
0x100415a23  movups  xmm0, xmmword ptr [rcx]
0x100415a26  lea     rax, [rsp+170h+var_120]
0x100415a2b  movups  xmm1, xmmword ptr [rcx+10h]
0x100415a2f  movups  xmmword ptr [rax], xmm0
0x100415a32  movups  xmm0, xmmword ptr [rcx+20h]
0x100415a36  movups  xmmword ptr [rax+10h], xmm1
0x100415a3a  movups  xmm1, xmmword ptr [rcx+30h]
0x100415a3e  movups  xmmword ptr [rax+20h], xmm0
0x100415a42  movups  xmm0, xmmword ptr [rcx+40h]
0x100415a46  movups  xmmword ptr [rax+30h], xmm1
0x100415a4a  movups  xmm1, xmmword ptr [rcx+50h]
0x100415a4e  movups  xmmword ptr [rax+40h], xmm0
0x100415a52  movups  xmm0, xmmword ptr [rcx+60h]
0x100415a56  movups  xmmword ptr [rax+50h], xmm1
0x100415a5a  movups  xmm1, xmmword ptr [rcx+80h]
0x100415a61  movups  xmmword ptr [rax+60h], xmm0
0x100415a65  lea     rax, [rax+80h]
0x100415a6c  movups  xmm0, xmmword ptr [rcx+70h]
0x100415a70  movups  xmmword ptr [rax-10h], xmm0
0x100415a74  movups  xmm0, xmmword ptr [rcx+90h]
0x100415a7b  movups  xmmword ptr [rax], xmm1
0x100415a7e  movups  xmm1, xmmword ptr [rcx+0A0h]
0x100415a85  movups  xmmword ptr [rax+10h], xmm0
0x100415a89  movups  xmm0, xmmword ptr [rcx+0B0h]
0x100415a90  movups  xmmword ptr [rax+20h], xmm1
0x100415a94  movups  xmm1, xmmword ptr [rcx+0C0h]
0x100415a9b  mov     rcx, cs:qword_10049F360
0x100415aa2  movups  xmmword ptr [rax+30h], xmm0
0x100415aa6  movups  xmmword ptr [rax+40h], xmm1
0x100415aaa  mov     rcx, [rcx+20h]
0x100415aae  movzx   edx, [rsp+170h+var_120]
0x100415ab3  call    cs:__imp_?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z; DBMgr::LookupDB(ulong)
0x100415ab9  test    rax, rax
0x100415abc  jz      short loc_100415AD8
0x100415abe  mov     rcx, rax
0x100415ac1  call    cs:__imp_?IsShuttingDown@DBTABLE@@QEBA_NXZ; DBTABLE::IsShuttingDown(void)
0x100415ac7  test    al, al
0x100415ac9  jz      short loc_100415AD8
0x100415acb  xor     bl, bl
0x100415acd  mov     ecx, 139Fh; dwErrCode
0x100415ad2  call    cs:__imp_SetLastError
0x100415ad8  mov     rdx, [rsp+170h+var_130]
0x100415add  jmp     short loc_100415AED
0x100415adf  mov     [rbp+70h+var_A8], 1
0x100415ae6  mov     [rbp+70h+var_A4], 1
0x100415aed  mov     eax, [rsp+170h+var_11C]
0x100415af1  bt      edi, 1Eh
0x100415af5  cmovb   eax, cs:dword_1004A0A18
0x100415afc  mov     [rsp+170h+var_11C], eax
0x100415b00  test    bl, bl
0x100415b02  jz      short loc_100415B30
0x100415b04  lea     rax, [rsp+170h+var_120]
0x100415b09  mov     r9, r15
0x100415b0c  mov     [rsp+170h+var_138], rax
0x100415b11  mov     r8d, r14d
0x100415b14  mov     [rsp+170h+var_140], rdx
0x100415b19  mov     rcx, rsi
0x100415b1c  mov     [rsp+170h+var_148], r13d
0x100415b21  mov     edx, edi
0x100415b23  mov     [rsp+170h+var_150], r12d
0x100415b28  call    cs:__imp_?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z; DBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,FCBFileDirectives const *)
0x100415b2e  jmp     short loc_100415B37
0x100415b30  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100415b37  mov     rcx, [rbp+70h+var_50]
0x100415b3b  xor     rcx, rsp; StackCookie
0x100415b3e  call    __security_check_cookie
0x100415b43  add     rsp, 138h
0x100415b4a  pop     r15
0x100415b4c  pop     r14
0x100415b4e  pop     r13
0x100415b50  pop     r12
0x100415b52  pop     rdi
0x100415b53  pop     rsi
0x100415b54  pop     rbx
0x100415b55  pop     rbp
0x100415b56  retn
```
