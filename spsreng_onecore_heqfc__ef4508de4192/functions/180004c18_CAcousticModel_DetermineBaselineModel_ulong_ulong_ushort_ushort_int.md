# CAcousticModel::DetermineBaselineModel(ulong,ulong *,ushort * *,ushort * *,int)

- ea: `0x180004c18`
- end: `0x180004eb3`
- name: `?DetermineBaselineModel@CAcousticModel@@AEAAJKPEAKPEAPEAG1H@Z`
- size: `667`
- prototype: `__int64 __usercall@<rax>(CAcousticModel *__hidden this@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800055f8`
- `0x1800056fc`
- `0x180005fb8`

## callees

- `0x180002db8`
- `0x180004a18`
- `0x180004b30`
- `0x180004c18`
- `0x180005524`
- `0x180005eb8`
- `0x1800061d0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e89`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAcousticModel::DetermineBaselineModel(
        CAcousticModel *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        int a6)
{
  int v8; // esi
  unsigned __int16 *v9; // rbx
  unsigned int v10; // r13d
  int v11; // r14d
  unsigned int i; // r15d
  int v13; // eax
  unsigned int j; // r14d
  unsigned __int16 *v15; // rax
  int v16; // r8d
  CAcousticModel *v17; // rcx
  unsigned __int16 *v19; // [rsp+28h] [rbp-38h]
  int v20; // [rsp+30h] [rbp-30h] BYREF
  int v21; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v22; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int *v27; // [rsp+B0h] [rbp+50h]
  unsigned __int16 **v28; // [rsp+B8h] [rbp+58h]

  v28 = a4;
  v27 = a3;
  v25[0] = 0;
  v22 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD *))(**(_QWORD **)(*((_QWORD *)this + 1) + 264LL) + 72LL))(
         *(_QWORD *)(*((_QWORD *)this + 1) + 264LL),
         L"AMs",
         v25);
  if ( v8 >= 0 )
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    for ( i = 0; ; ++i )
    {
      v23 = 0;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v25[0] + 112LL))(v25[0], i, &v23) < 0 )
        break;
      v13 = CAcousticModel::GoodnessOfMatch(this, v23, a2, &v22);
      if ( v13 > v11 )
      {
        v11 = v13;
        if ( v9 )
          CoTaskMemFree(v9);
        v9 = v23;
        v23 = 0;
        v10 = a2;
      }
      CSpDynamicString::_free((CSpDynamicString *)&v23);
    }
    CSpDynamicString::_free((CSpDynamicString *)&v23);
    if ( v11 )
    {
      if ( a6 )
      {
        *((_DWORD *)this + 7) = 0;
        for ( j = 0; ; ++j )
        {
          v24 = 0;
          v20 = 0;
          v21 = 0;
          v26 = 0;
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v25[0] + 112LL))(v25[0], j, &v24) < 0 )
            break;
          v15 = v24;
          do
          {
            v16 = *(unsigned __int16 *)((char *)v15 + (char *)v9 - (char *)v24);
            v17 = (CAcousticModel *)((unsigned int)*v15 - v16);
            if ( (_DWORD)v17 )
              break;
            ++v15;
          }
          while ( v16 );
          if ( (_DWORD)v17
            && *((int *)this + 7) < 15
            && (unsigned int)CAcousticModel::ParseAMName(
                               v17,
                               v24,
                               (enum MSAM_AGE *)&v21,
                               (enum MSAM_GENDER *)&v20,
                               &v26,
                               v19)
            && (v10 & v26) != 0 )
          {
            *((_DWORD *)this + 6 * *((int *)this + 7) + 29) = v20;
            *((_DWORD *)this + 6 * *((int *)this + 7) + 28) = v21;
            CSpDynamicString::operator=(
              (CAcousticModel *)((char *)this + 24 * *((int *)this + 7) + 96),
              (CSpDynamicString *)&v24);
            v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, char *))(*(_QWORD *)v25[0] + 48LL))(
                   v25[0],
                   v24,
                   (char *)this + 16 * *((int *)this + 7) + 8 * *((int *)this + 7) + 104);
            CSpDynamicString::AppendHR(
              (CAcousticModel *)((char *)this + 16 * *((int *)this + 7) + 8 * *((int *)this + 7) + 104),
              L".am");
            ++*((_DWORD *)this + 7);
          }
          CSpDynamicString::_free((CSpDynamicString *)&v24);
        }
        CSpDynamicString::_free((CSpDynamicString *)&v24);
      }
      if ( !a5
        || (v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)v25[0] + 48LL))(v25[0], v9), v8 >= 0) )
      {
        if ( v28 )
        {
          *v28 = v9;
          v9 = 0;
        }
        if ( v27 )
          *v27 = v22;
      }
    }
    else
    {
      v8 = -2147201021;
    }
    if ( v9 )
      CoTaskMemFree(v9);
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004c18  mov     [rsp-38h+arg_8], rbx
0x180004c1d  mov     [rsp-38h+arg_18], r9
0x180004c22  mov     [rsp-38h+arg_10], r8
0x180004c27  push    rbp
0x180004c28  push    rsi
0x180004c29  push    rdi
0x180004c2a  push    r12
0x180004c2c  push    r13
0x180004c2e  push    r14
0x180004c30  push    r15
0x180004c32  mov     rbp, rsp
0x180004c35  sub     rsp, 60h
0x180004c39  mov     r12d, edx
0x180004c3c  mov     rdi, rcx
0x180004c3f  mov     [rbp+var_10], 0
0x180004c47  mov     [rbp+var_28], 0
0x180004c4e  mov     rax, [rcx+8]
0x180004c52  mov     rcx, [rax+108h]
0x180004c59  mov     rax, [rcx]
0x180004c5c  lea     r8, [rbp+var_10]
0x180004c60  lea     rdx, aAms; "AMs"
0x180004c67  mov     rax, [rax+48h]
0x180004c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c70  mov     esi, eax
0x180004c72  test    eax, eax
0x180004c74  js      loc_180004E90
0x180004c7a  xor     ebx, ebx
0x180004c7c  xor     r13d, r13d
0x180004c7f  xor     r14d, r14d
0x180004c82  xor     r15d, r15d
0x180004c85  mov     [rbp+var_20], 0
0x180004c8d  mov     rcx, [rbp+var_10]
0x180004c91  mov     rax, [rcx]
0x180004c94  lea     r8, [rbp+var_20]
0x180004c98  mov     edx, r15d
0x180004c9b  mov     rax, [rax+70h]
0x180004c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca4  test    eax, eax
0x180004ca6  js      short loc_180004CEE
0x180004ca8  lea     r9, [rbp+var_28]; unsigned int *
0x180004cac  mov     r8d, r12d; unsigned int
0x180004caf  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180004cb3  mov     rcx, rdi; this
0x180004cb6  call    ?GoodnessOfMatch@CAcousticModel@@AEAAHPEBGKPEAK@Z; CAcousticModel::GoodnessOfMatch(ushort const *,ulong,ulong *)
0x180004cbb  cmp     eax, r14d
0x180004cbe  jle     short loc_180004CE0
0x180004cc0  mov     r14d, eax
0x180004cc3  test    rbx, rbx
0x180004cc6  jz      short loc_180004CD1
0x180004cc8  mov     rcx, rbx; pv
0x180004ccb  call    cs:__imp_CoTaskMemFree
0x180004cd1  mov     rbx, [rbp+var_20]
0x180004cd5  mov     [rbp+var_20], 0
0x180004cdd  mov     r13d, r12d
0x180004ce0  lea     rcx, [rbp+var_20]; this
0x180004ce4  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180004ce9  inc     r15d
0x180004cec  jmp     short loc_180004C85
0x180004cee  lea     rcx, [rbp+var_20]; this
0x180004cf2  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180004cf7  xor     r15d, r15d
0x180004cfa  test    r14d, r14d
0x180004cfd  jnz     short loc_180004D09
0x180004cff  mov     esi, 80045003h
0x180004d04  jmp     loc_180004E81
0x180004d09  cmp     [rbp+arg_28], r15d
0x180004d0d  jz      loc_180004E42
0x180004d13  mov     [rdi+1Ch], r15d
0x180004d17  mov     r14d, r15d
0x180004d1a  mov     [rbp+var_18], r15
0x180004d1e  mov     [rbp+var_30], r15d
0x180004d22  mov     [rbp+var_2C], r15d
0x180004d26  mov     [rbp+arg_0], r15d
0x180004d2a  mov     rcx, [rbp+var_10]
0x180004d2e  mov     rax, [rcx]
0x180004d31  lea     r8, [rbp+var_18]
0x180004d35  mov     edx, r14d
0x180004d38  mov     rax, [rax+70h]
0x180004d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d41  test    eax, eax
0x180004d43  js      loc_180004E39
0x180004d49  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180004d4d  mov     rax, rdx
0x180004d50  mov     r9, rbx
0x180004d53  sub     r9, rdx
0x180004d56  movzx   ecx, word ptr [rax]
0x180004d59  movzx   r8d, word ptr [rax+r9]
0x180004d5e  sub     ecx, r8d; this
0x180004d61  jnz     short loc_180004D6C
0x180004d63  add     rax, 2
0x180004d67  test    r8d, r8d
0x180004d6a  jnz     short loc_180004D56
0x180004d6c  test    ecx, ecx
0x180004d6e  jz      loc_180004E28
0x180004d74  cmp     dword ptr [rdi+1Ch], 0Fh
0x180004d78  jge     loc_180004E28
0x180004d7e  lea     rax, [rbp+arg_0]
0x180004d82  mov     [rsp+60h+var_40], rax; unsigned int *
0x180004d87  lea     r9, [rbp+var_30]; enum MSAM_GENDER *
0x180004d8b  lea     r8, [rbp+var_2C]; enum MSAM_AGE *
0x180004d8f  call    ?ParseAMName@CAcousticModel@@AEAAHPEBGPEAW4MSAM_AGE@@PEAW4MSAM_GENDER@@PEAKPEAG@Z; CAcousticModel::ParseAMName(ushort const *,MSAM_AGE *,MSAM_GENDER *,ulong *,ushort *)
0x180004d94  test    eax, eax
0x180004d96  jz      loc_180004E28
0x180004d9c  test    [rbp+arg_0], r13d
0x180004da0  jz      loc_180004E28
0x180004da6  movsxd  rax, dword ptr [rdi+1Ch]
0x180004daa  lea     rcx, [rax+rax*2]
0x180004dae  mov     eax, [rbp+var_30]
0x180004db1  mov     [rdi+rcx*8+74h], eax
0x180004db5  movsxd  rax, dword ptr [rdi+1Ch]
0x180004db9  lea     rcx, [rax+rax*2]
0x180004dbd  mov     eax, [rbp+var_2C]
0x180004dc0  mov     [rdi+rcx*8+70h], eax
0x180004dc4  movsxd  rax, dword ptr [rdi+1Ch]
0x180004dc8  add     rax, 4
0x180004dcc  lea     rax, [rax+rax*2]
0x180004dd0  lea     rcx, [rdi+rax*8]; this
0x180004dd4  lea     rdx, [rbp+var_18]; CSpDynamicString *
0x180004dd8  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x180004ddd  mov     rcx, [rbp+var_10]
0x180004de1  mov     r9, [rcx]
0x180004de4  movsxd  rax, dword ptr [rdi+1Ch]
0x180004de8  lea     r8, ds:0Dh[rax*2]
0x180004df0  add     r8, rax
0x180004df3  lea     r8, [rdi+r8*8]
0x180004df7  mov     rdx, [rbp+var_18]
0x180004dfb  mov     rax, [r9+30h]
0x180004dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e04  mov     esi, eax
0x180004e06  movsxd  rax, dword ptr [rdi+1Ch]
0x180004e0a  lea     rcx, ds:0Dh[rax*2]
0x180004e12  add     rcx, rax
0x180004e15  lea     rcx, [rdi+rcx*8]; this
0x180004e19  lea     rdx, aAm_0; ".am"
0x180004e20  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x180004e25  inc     dword ptr [rdi+1Ch]
0x180004e28  lea     rcx, [rbp+var_18]; this
0x180004e2c  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180004e31  inc     r14d
0x180004e34  jmp     loc_180004D1A
0x180004e39  lea     rcx, [rbp+var_18]; this
0x180004e3d  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180004e42  mov     r8, [rbp+arg_20]
0x180004e46  test    r8, r8
0x180004e49  jz      short loc_180004E64
0x180004e4b  mov     rcx, [rbp+var_10]
0x180004e4f  mov     rax, [rcx]
0x180004e52  mov     rdx, rbx
0x180004e55  mov     rax, [rax+30h]
0x180004e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5e  mov     esi, eax
0x180004e60  test    eax, eax
0x180004e62  js      short loc_180004E81
0x180004e64  mov     rax, [rbp+arg_18]
0x180004e68  test    rax, rax
0x180004e6b  jz      short loc_180004E73
0x180004e6d  mov     [rax], rbx
0x180004e70  mov     rbx, r15
0x180004e73  mov     rcx, [rbp+arg_10]
0x180004e77  test    rcx, rcx
0x180004e7a  jz      short loc_180004E81
0x180004e7c  mov     eax, [rbp+var_28]
0x180004e7f  mov     [rcx], eax
0x180004e81  test    rbx, rbx
0x180004e84  jz      short loc_180004E90
0x180004e86  mov     rcx, rbx; pv
0x180004e89  call    cs:__imp_CoTaskMemFree
0x180004e8f  nop
0x180004e90  lea     rcx, [rbp+var_10]
0x180004e94  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180004e99  mov     eax, esi
0x180004e9b  mov     rbx, [rsp+60h+arg_8]
0x180004ea3  add     rsp, 60h
0x180004ea7  pop     r15
0x180004ea9  pop     r14
0x180004eab  pop     r13
0x180004ead  pop     r12
0x180004eaf  pop     rdi
0x180004eb0  pop     rsi
0x180004eb1  pop     rbp
0x180004eb2  retn
```
