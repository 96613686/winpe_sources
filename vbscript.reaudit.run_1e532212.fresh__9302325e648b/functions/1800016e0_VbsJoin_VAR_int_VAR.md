# VbsJoin(VAR *,int,VAR *)

- ea: `0x1800016e0`
- end: `0x18000190e`
- name: `?VbsJoin@@YAJPEAVVAR@@H0@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800016e0`
- `0x1800037b0`
- `0x1800038c0`
- `0x18001d6c0`
- `0x18001d9c0`
- `0x18001fa40`
- `0x180035154`

## import_xrefs

- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180001888`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180001888`
- `OLEAUT32!SafeArrayAddRef` at `0x180001830`
- `OLEAUT32!SafeArrayAddRef` at `0x180001830`
- `OLEAUT32!SafeArrayReleaseData` at `0x180001879`
- `OLEAUT32!SafeArrayReleaseData` at `0x180001879`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000181c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001845`
- `OLEAUT32!__imp_SysFreeString` at `0x18000189a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000181c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001845`
- `OLEAUT32!__imp_SysFreeString` at `0x18000189a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800018e7`

## pseudocode

```c
__int64 __fastcall VbsJoin(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v4; // r14
  char v5; // di
  unsigned int v6; // esi
  OLECHAR *v7; // rbx
  const unsigned __int16 *v8; // r15
  int v9; // esi
  struct VAR *VarVal; // r13
  __int16 v11; // dx
  SAFEARRAY *v12; // rcx
  SAFEARRAY *v14; // rax
  unsigned __int16 *v15; // rsi
  HRESULT v16; // r14d
  int v17; // esi
  struct VAR *GcBstrVariant; // rax
  _BYTE v19[8]; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h]
  SAFEARRAY *psa; // [rsp+80h] [rbp+40h] BYREF
  PVOID ppDataToRelease; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 *v23; // [rsp+98h] [rbp+58h] BYREF

  v23 = 0;
  ppDataToRelease = 0;
  v4 = a3;
  *(_WORD *)a1 = 1;
  if ( (unsigned int)(a2 - 1) > 1 )
    return 2148139458LL;
  v5 = 0;
  v6 = 2;
  v7 = 0;
  v19[0] = 0;
  if ( a2 == 2 )
  {
    bstrString = VAR::BstrGetVal(a3);
    if ( bstrString == (BSTR)-1LL )
      return 2148139102LL;
    v4 = (struct VAR *)((char *)v4 + 24);
    BSTRHelper::CloneIfNeeded((BSTRHelper *)v19, v4);
    v7 = bstrString;
    LODWORD(v8) = (_DWORD)bstrString;
    if ( bstrString )
      v9 = *((_DWORD *)bstrString - 1);
    else
      v9 = 0;
    v5 = v19[0];
    v6 = v9 & 0xFFFFFFFE;
  }
  else
  {
    v8 = L" ";
  }
  VarVal = VAR::PvarGetVarVal(v4, 0);
  v11 = *(_WORD *)VarVal;
  if ( *(_WORD *)VarVal == 1 )
  {
LABEL_13:
    if ( v5 )
      SysFreeString(v7);
    return 2148139102LL;
  }
  if ( ((v11 - 8204) & 0xBFFF) != 0 )
    goto LABEL_22;
  v12 = (SAFEARRAY *)*((_QWORD *)VarVal + 1);
  psa = v12;
  if ( (v11 & 0x4000) != 0 )
  {
    if ( !v12 )
      goto LABEL_13;
    v14 = *(SAFEARRAY **)&v12->cDims;
    v12 = v14;
    psa = v14;
  }
  else
  {
    v14 = v12;
  }
  if ( !v14 )
  {
    v15 = _SysAllocStringLen(0, 0);
    if ( !v15 )
    {
LABEL_40:
      if ( v5 )
        SysFreeString(v7);
      return 2148139015LL;
    }
    goto LABEL_38;
  }
  if ( v12->cDims != 1 )
  {
LABEL_22:
    if ( v5 )
      SysFreeString(v7);
    return 2148139021LL;
  }
  v16 = SafeArrayAddRef(v12, &ppDataToRelease);
  if ( v16 < 0 )
  {
    if ( v5 )
      SysFreeString(v7);
    return (unsigned int)v16;
  }
  v17 = rtJoin((_DWORD)VarVal, (unsigned int)&psa, (_DWORD)v8, v6, (__int64)&v23);
  if ( ppDataToRelease )
    SafeArrayReleaseData(ppDataToRelease);
  if ( psa )
    SafeArrayReleaseDescriptor(psa);
  if ( v17 < 0 )
  {
    if ( v5 )
      SysFreeString(v7);
    return (unsigned int)v17;
  }
  v15 = v23;
LABEL_38:
  *(_WORD *)a1 = 74;
  GcBstrVariant = MakeGcBstrVariant(v15);
  *((_QWORD *)a1 + 1) = GcBstrVariant;
  if ( !GcBstrVariant )
  {
    SysFreeString(v15);
    goto LABEL_40;
  }
  if ( v5 )
    SysFreeString(v7);
  return 0;
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp-38h+arg_8], rbx
0x1800016e5  push    rbp
0x1800016e6  push    rsi
0x1800016e7  push    rdi
0x1800016e8  push    r12
0x1800016ea  push    r13
0x1800016ec  push    r14
0x1800016ee  push    r15
0x1800016f0  mov     rbp, rsp
0x1800016f3  sub     rsp, 40h
0x1800016f7  mov     r12, rcx
0x1800016fa  mov     [rbp+arg_18], 0
0x180001702  mov     ecx, 1
0x180001707  mov     [rbp+ppDataToRelease], 0
0x18000170f  lea     eax, [rdx-1]
0x180001712  mov     r14, r8
0x180001715  mov     [r12], cx
0x18000171a  cmp     eax, ecx
0x18000171c  ja      loc_1800018F1
0x180001722  xor     dil, dil
0x180001725  lea     esi, [rcx+1]
0x180001728  xor     ebx, ebx
0x18000172a  mov     [rbp+var_10], dil
0x18000172e  cmp     edx, esi
0x180001730  jnz     short loc_180001774
0x180001732  mov     rcx, r8; this
0x180001735  call    ?BstrGetVal@VAR@@QEAAPEAGXZ; VAR::BstrGetVal(void)
0x18000173a  mov     [rbp+bstrString], rax
0x18000173e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001742  jz      loc_1800017D6
0x180001748  add     r14, 18h
0x18000174c  lea     rcx, [rbp+var_10]; this
0x180001750  mov     rdx, r14; struct VAR *
0x180001753  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x180001758  mov     rbx, [rbp+bstrString]
0x18000175c  mov     r15, rbx
0x18000175f  test    rbx, rbx
0x180001762  jnz     short loc_180001768
0x180001764  xor     esi, esi
0x180001766  jmp     short loc_18000176B
0x180001768  mov     esi, [rbx-4]
0x18000176b  mov     dil, [rbp+var_10]
0x18000176f  and     esi, 0FFFFFFFEh
0x180001772  jmp     short loc_18000177B
0x180001774  lea     r15, asc_1800812E0; " "
0x18000177b  xor     edx, edx; int
0x18000177d  mov     rcx, r14; this
0x180001780  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x180001785  mov     r8d, 1
0x18000178b  mov     r13, rax
0x18000178e  movzx   edx, word ptr [rax]
0x180001791  cmp     r8w, dx
0x180001795  jz      short loc_1800017C8
0x180001797  mov     ecx, 200Ch
0x18000179c  movzx   eax, dx
0x18000179f  sub     ax, cx
0x1800017a2  mov     ecx, 0BFFFh
0x1800017a7  test    cx, ax
0x1800017aa  jnz     short loc_180001814
0x1800017ac  mov     rcx, [r13+8]; psa
0x1800017b0  mov     eax, 4000h
0x1800017b5  and     dx, ax
0x1800017b8  mov     [rbp+psa], rcx
0x1800017bc  xor     eax, eax
0x1800017be  cmp     ax, dx
0x1800017c1  jz      short loc_1800017EC
0x1800017c3  test    rcx, rcx
0x1800017c6  jnz     short loc_1800017E0
0x1800017c8  test    dil, dil
0x1800017cb  jz      short loc_1800017D6
0x1800017cd  mov     rcx, rbx; bstrString
0x1800017d0  call    cs:__imp_SysFreeString
0x1800017d6  mov     eax, 800A005Eh
0x1800017db  jmp     loc_1800018F6
0x1800017e0  mov     rax, [rcx]
0x1800017e3  mov     rcx, rax
0x1800017e6  mov     [rbp+psa], rax
0x1800017ea  jmp     short loc_1800017EF
0x1800017ec  mov     rax, rcx
0x1800017ef  test    rax, rax
0x1800017f2  jnz     short loc_18000180E
0x1800017f4  xor     edx, edx; unsigned int
0x1800017f6  xor     ecx, ecx; unsigned __int16 *
0x1800017f8  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800017fd  mov     rsi, rax
0x180001800  test    rax, rax
0x180001803  jz      loc_1800018CA
0x180001809  jmp     loc_1800018A8
0x18000180e  cmp     r8w, [rcx]
0x180001812  jz      short loc_18000182C
0x180001814  test    dil, dil
0x180001817  jz      short loc_180001822
0x180001819  mov     rcx, rbx; bstrString
0x18000181c  call    cs:__imp_SysFreeString
0x180001822  mov     eax, 800A000Dh
0x180001827  jmp     loc_1800018F6
0x18000182c  lea     rdx, [rbp+ppDataToRelease]; ppDataToRelease
0x180001830  call    cs:__imp_SafeArrayAddRef
0x180001836  mov     r14d, eax
0x180001839  test    eax, eax
0x18000183b  jns     short loc_180001853
0x18000183d  test    dil, dil
0x180001840  jz      short loc_18000184B
0x180001842  mov     rcx, rbx; bstrString
0x180001845  call    cs:__imp_SysFreeString
0x18000184b  mov     eax, r14d
0x18000184e  jmp     loc_1800018F6
0x180001853  lea     rax, [rbp+arg_18]
0x180001857  mov     r9d, esi
0x18000185a  mov     r8, r15
0x18000185d  mov     [rsp+40h+var_20], rax
0x180001862  lea     rdx, [rbp+psa]
0x180001866  mov     rcx, r13
0x180001869  call    rtJoin
0x18000186e  mov     rcx, [rbp+ppDataToRelease]; pData
0x180001872  mov     esi, eax
0x180001874  test    rcx, rcx
0x180001877  jz      short loc_18000187F
0x180001879  call    cs:__imp_SafeArrayReleaseData
0x18000187f  mov     rcx, [rbp+psa]; psa
0x180001883  test    rcx, rcx
0x180001886  jz      short loc_18000188E
0x180001888  call    cs:__imp_SafeArrayReleaseDescriptor
0x18000188e  test    esi, esi
0x180001890  jns     short loc_1800018A4
0x180001892  test    dil, dil
0x180001895  jz      short loc_1800018A0
0x180001897  mov     rcx, rbx; bstrString
0x18000189a  call    cs:__imp_SysFreeString
0x1800018a0  mov     eax, esi
0x1800018a2  jmp     short loc_1800018F6
0x1800018a4  mov     rsi, [rbp+arg_18]
0x1800018a8  mov     rcx, rsi; unsigned __int16 *
0x1800018ab  mov     word ptr [r12], 4Ah ; 'J'
0x1800018b2  call    ?MakeGcBstrVariant@@YAPEAVVAR@@PEAG@Z; MakeGcBstrVariant(ushort *)
0x1800018b7  mov     [r12+8], rax
0x1800018bc  test    rax, rax
0x1800018bf  jnz     short loc_1800018DF
0x1800018c1  mov     rcx, rsi; bstrString
0x1800018c4  call    cs:__imp_SysFreeString
0x1800018ca  test    dil, dil
0x1800018cd  jz      short loc_1800018D8
0x1800018cf  mov     rcx, rbx; bstrString
0x1800018d2  call    cs:__imp_SysFreeString
0x1800018d8  mov     eax, 800A0007h
0x1800018dd  jmp     short loc_1800018F6
0x1800018df  test    dil, dil
0x1800018e2  jz      short loc_1800018ED
0x1800018e4  mov     rcx, rbx; bstrString
0x1800018e7  call    cs:__imp_SysFreeString
0x1800018ed  xor     eax, eax
0x1800018ef  jmp     short loc_1800018F6
0x1800018f1  mov     eax, 800A01C2h
0x1800018f6  mov     rbx, [rsp+40h+arg_8]
0x1800018fe  add     rsp, 40h
0x180001902  pop     r15
0x180001904  pop     r14
0x180001906  pop     r13
0x180001908  pop     r12
0x18000190a  pop     rdi
0x18000190b  pop     rsi
0x18000190c  pop     rbp
0x18000190d  retn
```
