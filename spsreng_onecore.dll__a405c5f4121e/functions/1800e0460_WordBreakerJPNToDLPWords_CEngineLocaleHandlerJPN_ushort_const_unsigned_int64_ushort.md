# WordBreakerJPNToDLPWords(CEngineLocaleHandlerJPN *,ushort const *,unsigned __int64,ushort * *)

- ea: `0x1800e0460`
- end: `0x1800e0652`
- name: `?WordBreakerJPNToDLPWords@@YAJPEAVCEngineLocaleHandlerJPN@@PEBG_KPEAPEAG@Z`
- size: `498`
- prototype: `__int64 __fastcall(struct CEngineLocaleHandlerJPN *, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db670`

## callees

- `0x1800034b0`
- `0x180007378`
- `0x1800c77ac`
- `0x1800ddd08`
- `0x1800e0234`
- `0x1800e0460`
- `0x1800e0658`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e05df`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e05df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e04d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e04d1`

## pseudocode

```c
__int64 __fastcall WordBreakerJPNToDLPWords(
        struct CEngineLocaleHandlerJPN *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  unsigned int v5; // edx
  int v6; // ebx
  DLPToken *v7; // rdi
  int v8; // esi
  __int64 v9; // rdx
  int i; // esi
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  DLPToken *v15; // [rsp+50h] [rbp-B0h] BYREF
  void **v16; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR *strIn; // [rsp+68h] [rbp-98h]
  unsigned int v18; // [rsp+70h] [rbp-90h]
  __int16 v19; // [rsp+78h] [rbp-88h] BYREF

  v13 = 0;
  v12 = 0;
  v15 = 0;
  pv = 0;
  v6 = WordBreakerJPNToDLPTokens(a1, a2, a3, &v13, &v12, &v15, (struct tagMORRSLT **)&pv);
  if ( pv )
    CoTaskMemFree(pv);
  v7 = v15;
  if ( v6 >= 0 )
  {
    if ( !v15 )
      return (unsigned int)v6;
    if ( v12 > 0 )
    {
      v18 = 0x80000000;
      strIn = (OLECHAR *)&v19;
      v16 = &CQuickStringW<100>::`vftable';
      v8 = 0;
      v19 = 0;
      while ( v6 >= 0 )
      {
        if ( (int)CQuickStringW<100>::Append(&v16, L"/") >= 0
          && (int)CQuickStringW<100>::Append(&v16, *((_QWORD *)v7 + 6 * v8 + 2)) >= 0
          && (int)CQuickStringW<100>::Append(&v16, L"/") >= 0
          && (int)CQuickStringW<100>::Append(&v16, *((_QWORD *)v7 + 6 * v8 + 3)) >= 0 )
        {
          CQuickStringW<100>::Append(&v16, L"/");
        }
        v6 = CQuickStringW<100>::Append(&v16, *((_QWORD *)v7 + 6 * v8 + 4));
        if ( v6 >= 0 )
          v6 = CQuickStringW<100>::Append(&v16, L";");
        if ( ++v8 >= v12 )
        {
          if ( v6 >= 0 )
          {
            v9 = -1;
            do
              ++v9;
            while ( strIn[v9] );
            *a4 = SysAllocStringLen(strIn, v9);
          }
          break;
        }
      }
      if ( !*a4 )
        v6 = -2147024882;
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v16);
    }
  }
  if ( v7 )
  {
    for ( i = 0; i < v13; ++i )
      DLPToken::clean((DLPToken *)((char *)v7 + 48 * i));
    DLPToken::`vector deleting destructor'(v7, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e0460  push    rbp
0x1800e0462  push    rbx
0x1800e0463  push    rsi
0x1800e0464  push    rdi
0x1800e0465  push    r12
0x1800e0467  push    r15
0x1800e0469  lea     rbp, [rsp-68h]
0x1800e046e  sub     rsp, 168h
0x1800e0475  mov     rax, cs:__security_cookie
0x1800e047c  xor     rax, rsp
0x1800e047f  mov     [rbp+90h+var_40], rax
0x1800e0483  xor     r12d, r12d
0x1800e0486  lea     rax, [rsp+190h+pv]
0x1800e048b  mov     [rsp+190h+var_160], rax; struct tagMORRSLT **
0x1800e0490  mov     r15, r9
0x1800e0493  lea     rax, [rsp+190h+var_140]
0x1800e0498  mov     [rsp+190h+var_14C], r12d
0x1800e049d  mov     [rsp+190h+var_168], rax; struct DLPToken **
0x1800e04a2  lea     r9, [rsp+190h+var_14C]; int *
0x1800e04a7  lea     rax, [rsp+190h+var_150]
0x1800e04ac  mov     [rsp+190h+var_150], r12d
0x1800e04b1  mov     [rsp+190h+var_170], rax; int *
0x1800e04b6  mov     [rsp+190h+var_140], r12
0x1800e04bb  mov     [rsp+190h+pv], r12
0x1800e04c0  call    ?WordBreakerJPNToDLPTokens@@YAJPEAVCEngineLocaleHandlerJPN@@PEBG_KPEAH3PEAPEAVDLPToken@@PEAPEAUtagMORRSLT@@@Z; WordBreakerJPNToDLPTokens(CEngineLocaleHandlerJPN *,ushort const *,unsigned __int64,int *,int *,DLPToken * *,tagMORRSLT * *)
0x1800e04c5  mov     rcx, [rsp+190h+pv]; pv
0x1800e04ca  mov     ebx, eax
0x1800e04cc  test    rcx, rcx
0x1800e04cf  jz      short loc_1800E04D7
0x1800e04d1  call    cs:__imp_CoTaskMemFree
0x1800e04d7  mov     rdi, [rsp+190h+var_140]
0x1800e04dc  test    ebx, ebx
0x1800e04de  js      loc_1800E05FD
0x1800e04e4  test    rdi, rdi
0x1800e04e7  jz      loc_1800E0634
0x1800e04ed  cmp     [rsp+190h+var_150], r12d
0x1800e04f2  jle     loc_1800E05FD
0x1800e04f8  lea     rcx, [rsp+190h+var_118]
0x1800e04fd  mov     [rsp+190h+var_120], 80000000h
0x1800e0505  lea     rax, ??_7?$CQuickStringW@$0GE@@@6B@; const CQuickStringW<100>::`vftable'
0x1800e050c  mov     [rsp+190h+strIn], rcx
0x1800e0511  mov     [rsp+190h+var_130], rax
0x1800e0516  mov     esi, r12d
0x1800e0519  mov     [rsp+190h+var_118], r12w
0x1800e051f  test    ebx, ebx
0x1800e0521  js      loc_1800E05E8
0x1800e0527  lea     rdx, asc_1801151AC; "/"
0x1800e052e  lea     rcx, [rsp+190h+var_130]
0x1800e0533  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e0538  movsxd  rcx, esi
0x1800e053b  lea     rbx, [rcx+rcx*2]
0x1800e053f  add     rbx, rbx
0x1800e0542  test    eax, eax
0x1800e0544  js      short loc_1800E0592
0x1800e0546  mov     rdx, [rdi+rbx*8+10h]
0x1800e054b  lea     rcx, [rsp+190h+var_130]
0x1800e0550  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e0555  test    eax, eax
0x1800e0557  js      short loc_1800E0592
0x1800e0559  lea     rdx, asc_1801151AC; "/"
0x1800e0560  lea     rcx, [rsp+190h+var_130]
0x1800e0565  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e056a  test    eax, eax
0x1800e056c  js      short loc_1800E0592
0x1800e056e  mov     rdx, [rdi+rbx*8+18h]
0x1800e0573  lea     rcx, [rsp+190h+var_130]
0x1800e0578  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e057d  test    eax, eax
0x1800e057f  js      short loc_1800E0592
0x1800e0581  lea     rdx, asc_1801151AC; "/"
0x1800e0588  lea     rcx, [rsp+190h+var_130]
0x1800e058d  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e0592  mov     rdx, [rdi+rbx*8+20h]
0x1800e0597  lea     rcx, [rsp+190h+var_130]
0x1800e059c  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e05a1  mov     ebx, eax
0x1800e05a3  test    eax, eax
0x1800e05a5  js      short loc_1800E05BA
0x1800e05a7  lea     rdx, Control; ";"
0x1800e05ae  lea     rcx, [rsp+190h+var_130]
0x1800e05b3  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800e05b8  mov     ebx, eax
0x1800e05ba  inc     esi
0x1800e05bc  mov     eax, ebx
0x1800e05be  cmp     esi, [rsp+190h+var_150]
0x1800e05c2  jl      loc_1800E051F
0x1800e05c8  test    eax, eax
0x1800e05ca  js      short loc_1800E05E8
0x1800e05cc  mov     rcx, [rsp+190h+strIn]; strIn
0x1800e05d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e05d5  inc     rdx; ui
0x1800e05d8  cmp     [rcx+rdx*2], r12w
0x1800e05dd  jnz     short loc_1800E05D5
0x1800e05df  call    cs:__imp_SysAllocStringLen
0x1800e05e5  mov     [r15], rax
0x1800e05e8  cmp     [r15], r12
0x1800e05eb  lea     rcx, [rsp+190h+var_130]; this
0x1800e05f0  mov     eax, 8007000Eh
0x1800e05f5  cmovz   ebx, eax
0x1800e05f8  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x1800e05fd  test    rdi, rdi
0x1800e0600  jz      short loc_1800E0634
0x1800e0602  mov     esi, r12d
0x1800e0605  cmp     [rsp+190h+var_14C], r12d
0x1800e060a  jle     short loc_1800E0627
0x1800e060c  movsxd  rax, esi
0x1800e060f  lea     rcx, [rax+rax*2]
0x1800e0613  shl     rcx, 4
0x1800e0617  add     rcx, rdi; this
0x1800e061a  call    ?clean@DLPToken@@QEAAXXZ; DLPToken::clean(void)
0x1800e061f  inc     esi
0x1800e0621  cmp     esi, [rsp+190h+var_14C]
0x1800e0625  jl      short loc_1800E060C
0x1800e0627  test    rdi, rdi
0x1800e062a  jz      short loc_1800E0634
0x1800e062c  mov     rcx, rdi; this
0x1800e062f  call    ??_EDLPToken@@QEAAPEAXI@Z; DLPToken::`vector deleting destructor'(uint)
0x1800e0634  mov     eax, ebx
0x1800e0636  mov     rcx, [rbp+90h+var_40]
0x1800e063a  xor     rcx, rsp; StackCookie
0x1800e063d  call    __security_check_cookie
0x1800e0642  add     rsp, 168h
0x1800e0649  pop     r15
0x1800e064b  pop     r12
0x1800e064d  pop     rdi
0x1800e064e  pop     rsi
0x1800e064f  pop     rbx
0x1800e0650  pop     rbp
0x1800e0651  retn
```
