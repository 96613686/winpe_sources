# VbsFilter(VAR *,int,VAR *)

- ea: `0x180075400`
- end: `0x180075630`
- name: `?VbsFilter@@YAJPEAVVAR@@H0@Z`
- size: `560`
- prototype: `int(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180017138`
- `0x1800178e0`
- `0x180018aa0`
- `0x180019650`
- `0x18001a260`
- `0x180025090`
- `0x1800260a0`
- `0x1800261b8`
- `0x18003a480`
- `0x180075400`
- `0x180075dd4`

## import_xrefs

- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x1800755ad`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x1800755ad`
- `OLEAUT32!SafeArrayAddRef` at `0x180075552`
- `OLEAUT32!SafeArrayAddRef` at `0x180075552`
- `OLEAUT32!SafeArrayReleaseData` at `0x180075598`
- `OLEAUT32!SafeArrayReleaseData` at `0x180075598`
- `KERNEL32!IsValidLocale` at `0x180075461`
- `KERNEL32!IsValidLocale` at `0x180075461`

## pseudocode

```c
__int64 __fastcall VbsFilter(struct VAR *a1, int a2, VARIANTARG *a3)
{
  VARIANTARG *v3; // rbx
  LCID Val; // eax
  unsigned int ConversionLocale; // edi
  int v9; // r14d
  struct VAR *TypeVal; // rax
  int v11; // esi
  struct VAR *VarVal; // r12
  __int16 v13; // dx
  SAFEARRAY *v14; // rcx
  SAFEARRAY *v15; // rax
  int v16; // ebx
  struct tagSAFEARRAY *OneDim; // rbx
  struct VAR *v18; // rax
  _BYTE v19[8]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-8h]
  SAFEARRAY *psa; // [rsp+90h] [rbp+40h] BYREF
  PVOID ppDataToRelease; // [rsp+A0h] [rbp+50h] BYREF
  SAFEARRAY *v23; // [rsp+A8h] [rbp+58h] BYREF

  v23 = 0;
  ppDataToRelease = 0;
  *(_WORD *)a1 = 1;
  v3 = a3;
  if ( (unsigned int)(a2 - 2) <= 2 )
  {
    if ( a2 == 4 )
    {
      Val = VAR::UlGetVal((VAR *)a3);
      ++v3;
      ConversionLocale = Val;
      if ( Val >= 2 )
      {
        if ( !IsValidLocale(Val, 1u) )
          return 2148139013LL;
        v9 = 1;
        goto LABEL_10;
      }
      v9 = Val;
    }
    else
    {
      v9 = 0;
    }
    ConversionLocale = COleScript::GetConversionLocale();
    if ( a2 < 3 )
    {
      v11 = 1;
      goto LABEL_12;
    }
LABEL_10:
    TypeVal = VAR::PvarGetTypeVal(v3++, 0xBu);
    v11 = *((__int16 *)TypeVal + 4);
LABEL_12:
    v19[0] = 0;
    v20 = VAR::BstrGetVal((VAR *)v3);
    if ( v20 != (unsigned __int16 *)-1LL )
    {
      BSTRHelper::CloneIfNeeded((BSTRHelper *)v19, (struct VAR *)&v3[1]);
      VarVal = VAR::PvarGetVarVal((VAR *)&v3[1], 0);
      v13 = *(_WORD *)VarVal;
      if ( *(_WORD *)VarVal != 1 )
      {
        if ( ((v13 - 8204) & 0xBFFF) != 0 )
          goto LABEL_32;
        v14 = (SAFEARRAY *)*((_QWORD *)VarVal + 1);
        psa = v14;
        if ( (v13 & 0x4000) == 0 )
        {
          v15 = v14;
LABEL_19:
          if ( !v15 )
          {
            OneDim = psaMakeOneDim(0);
            goto LABEL_29;
          }
          if ( v14->cDims == 1 )
          {
            v16 = SafeArrayAddRef(v14, &ppDataToRelease);
            if ( v16 >= 0 )
            {
              v16 = rtFilter(VarVal, &psa, (__int64)v20, v11, ConversionLocale, v9, &v23);
              if ( ppDataToRelease )
                SafeArrayReleaseData(ppDataToRelease);
              if ( psa )
                SafeArrayReleaseDescriptor(psa);
              if ( v16 >= 0 )
              {
                OneDim = v23;
LABEL_29:
                v18 = PvarAlloc();
                *((_QWORD *)a1 + 1) = v18;
                if ( v18 )
                {
                  *(_WORD *)v18 = 8204;
                  *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL) = OneDim;
                  *(_WORD *)a1 = 74;
                  BSTRHelper::~BSTRHelper((BSTRHelper *)v19);
                  return 0;
                }
                v16 = -2146828281;
              }
            }
LABEL_34:
            BSTRHelper::~BSTRHelper((BSTRHelper *)v19);
            return (unsigned int)v16;
          }
LABEL_32:
          v16 = -2146828275;
          goto LABEL_34;
        }
        if ( v14 )
        {
          v15 = *(SAFEARRAY **)&v14->cDims;
          v14 = v15;
          psa = v15;
          goto LABEL_19;
        }
      }
    }
    v16 = -2146828194;
    goto LABEL_34;
  }
  return 2148139458LL;
}

```

## disassembly

```asm
0x180075400  push    rbp
0x180075402  push    rbx
0x180075403  push    rsi
0x180075404  push    rdi
0x180075405  push    r12
0x180075407  push    r14
0x180075409  push    r15
0x18007540b  mov     rbp, rsp
0x18007540e  sub     rsp, 50h
0x180075412  lea     eax, [rdx-2]
0x180075415  mov     [rbp+arg_18], 0
0x18007541d  mov     [rbp+ppDataToRelease], 0
0x180075425  mov     r12d, 1
0x18007542b  mov     [rcx], r12w
0x18007542f  mov     rbx, r8
0x180075432  mov     esi, edx
0x180075434  mov     r15, rcx
0x180075437  cmp     eax, 2
0x18007543a  ja      loc_18007561B
0x180075440  cmp     edx, 4
0x180075443  jnz     short loc_180075485
0x180075445  mov     rcx, rbx; this
0x180075448  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x18007544d  add     rbx, 18h
0x180075451  mov     edi, eax
0x180075453  test    eax, eax
0x180075455  jz      short loc_180075480
0x180075457  cmp     eax, r12d
0x18007545a  jz      short loc_180075480
0x18007545c  mov     edx, r12d; dwFlags
0x18007545f  mov     ecx, eax; Locale
0x180075461  call    cs:__imp_IsValidLocale
0x180075468  nop     dword ptr [rax+rax+00h]
0x18007546d  test    eax, eax
0x18007546f  jnz     short loc_18007547B
0x180075471  mov     eax, 800A0005h
0x180075476  jmp     loc_180075620
0x18007547b  mov     r14d, r12d
0x18007547e  jmp     short loc_180075494
0x180075480  mov     r14d, eax
0x180075483  jmp     short loc_180075488
0x180075485  xor     r14d, r14d
0x180075488  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18007548d  mov     edi, eax
0x18007548f  cmp     esi, 3
0x180075492  jl      short loc_1800754AB
0x180075494  mov     edx, 0Bh; unsigned __int16
0x180075499  mov     rcx, rbx; pvarSrc
0x18007549c  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x1800754a1  add     rbx, 18h
0x1800754a5  movsx   esi, word ptr [rax+8]
0x1800754a9  jmp     short loc_1800754AE
0x1800754ab  mov     esi, r12d
0x1800754ae  mov     rcx, rbx; this
0x1800754b1  mov     [rbp+var_10], 0
0x1800754b5  call    ?BstrGetVal@VAR@@QEAAPEAGXZ; VAR::BstrGetVal(void)
0x1800754ba  mov     [rbp+var_8], rax
0x1800754be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800754c2  jz      loc_180075609
0x1800754c8  lea     rdx, [rbx+18h]; struct VAR *
0x1800754cc  lea     rcx, [rbp+var_10]; this
0x1800754d0  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x1800754d5  xor     edx, edx; int
0x1800754d7  lea     rcx, [rbx+18h]; this
0x1800754db  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x1800754e0  mov     r8d, 1
0x1800754e6  mov     r12, rax
0x1800754e9  movzx   edx, word ptr [rax]
0x1800754ec  cmp     r8w, dx
0x1800754f0  jz      loc_180075609
0x1800754f6  mov     eax, 200Ch
0x1800754fb  movzx   ecx, dx
0x1800754fe  sub     cx, ax
0x180075501  mov     eax, 0BFFFh
0x180075506  test    ax, cx
0x180075509  jnz     loc_180075602
0x18007550f  mov     rcx, [r12+8]; psa
0x180075514  mov     eax, 4000h
0x180075519  and     dx, ax
0x18007551c  mov     [rbp+psa], rcx
0x180075520  xor     eax, eax
0x180075522  cmp     ax, dx
0x180075525  jz      short loc_18007553C
0x180075527  test    rcx, rcx
0x18007552a  jz      loc_180075609
0x180075530  mov     rax, [rcx]
0x180075533  mov     rcx, rax
0x180075536  mov     [rbp+psa], rax
0x18007553a  jmp     short loc_18007553F
0x18007553c  mov     rax, rcx
0x18007553f  test    rax, rax
0x180075542  jz      short loc_1800755C3
0x180075544  cmp     r8w, [rcx]
0x180075548  jnz     loc_180075602
0x18007554e  lea     rdx, [rbp+ppDataToRelease]; ppDataToRelease
0x180075552  call    cs:__imp_SafeArrayAddRef
0x180075559  nop     dword ptr [rax+rax+00h]
0x18007555e  mov     ebx, eax
0x180075560  test    eax, eax
0x180075562  js      loc_18007560E
0x180075568  mov     r8, [rbp+var_8]
0x18007556c  lea     rax, [rbp+arg_18]
0x180075570  mov     [rsp+50h+var_20], rax
0x180075575  lea     rdx, [rbp+psa]
0x180075579  mov     [rsp+50h+var_28], r14d
0x18007557e  mov     r9d, esi
0x180075581  mov     rcx, r12
0x180075584  mov     [rsp+50h+var_30], edi
0x180075588  call    rtFilter
0x18007558d  mov     rcx, [rbp+ppDataToRelease]; pData
0x180075591  mov     ebx, eax
0x180075593  test    rcx, rcx
0x180075596  jz      short loc_1800755A4
0x180075598  call    cs:__imp_SafeArrayReleaseData
0x18007559f  nop     dword ptr [rax+rax+00h]
0x1800755a4  mov     rcx, [rbp+psa]; psa
0x1800755a8  test    rcx, rcx
0x1800755ab  jz      short loc_1800755B9
0x1800755ad  call    cs:__imp_SafeArrayReleaseDescriptor
0x1800755b4  nop     dword ptr [rax+rax+00h]
0x1800755b9  test    ebx, ebx
0x1800755bb  js      short loc_18007560E
0x1800755bd  mov     rbx, [rbp+arg_18]
0x1800755c1  jmp     short loc_1800755CD
0x1800755c3  xor     ecx, ecx; int
0x1800755c5  call    ?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z; psaMakeOneDim(long)
0x1800755ca  mov     rbx, rax
0x1800755cd  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x1800755d2  mov     [r15+8], rax
0x1800755d6  test    rax, rax
0x1800755d9  jnz     short loc_1800755E2
0x1800755db  mov     ebx, 800A0007h
0x1800755e0  jmp     short loc_18007560E
0x1800755e2  mov     word ptr [rax], 200Ch
0x1800755e7  lea     rcx, [rbp+var_10]; this
0x1800755eb  mov     rax, [r15+8]
0x1800755ef  mov     [rax+8], rbx
0x1800755f3  mov     word ptr [r15], 4Ah ; 'J'
0x1800755f9  call    ??1BSTRHelper@@QEAA@XZ; BSTRHelper::~BSTRHelper(void)
0x1800755fe  xor     eax, eax
0x180075600  jmp     short loc_180075620
0x180075602  mov     ebx, 800A000Dh
0x180075607  jmp     short loc_18007560E
0x180075609  mov     ebx, 800A005Eh
0x18007560e  lea     rcx, [rbp+var_10]; this
0x180075612  call    ??1BSTRHelper@@QEAA@XZ; BSTRHelper::~BSTRHelper(void)
0x180075617  mov     eax, ebx
0x180075619  jmp     short loc_180075620
0x18007561b  mov     eax, 800A01C2h
0x180075620  add     rsp, 50h
0x180075624  pop     r15
0x180075626  pop     r14
0x180075628  pop     r12
0x18007562a  pop     rdi
0x18007562b  pop     rsi
0x18007562c  pop     rbx
0x18007562d  pop     rbp
0x18007562e  retn
```
