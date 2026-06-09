# VbsJoin(VAR *,int,VAR *)

- ea: `0x1800266c0`
- end: `0x1800268af`
- name: `?VbsJoin@@YAJPEAVVAR@@H0@Z`
- size: `495`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180011650`
- `0x1800178e0`
- `0x180017bf8`
- `0x180019d50`
- `0x180025090`
- `0x1800260a0`
- `0x1800266c0`
- `0x18003a480`

## import_xrefs

- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180026835`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180026835`
- `OLEAUT32!SafeArrayAddRef` at `0x1800267e4`
- `OLEAUT32!SafeArrayAddRef` at `0x1800267e4`
- `OLEAUT32!SafeArrayReleaseData` at `0x180026820`
- `OLEAUT32!SafeArrayReleaseData` at `0x180026820`
- `OLEAUT32!__imp_SysFreeString` at `0x180026863`
- `OLEAUT32!__imp_SysFreeString` at `0x180026863`

## pseudocode

```c
__int64 __fastcall VbsJoin(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v3; // rbx
  unsigned int v5; // edi
  unsigned __int16 *v6; // rsi
  int v7; // edi
  struct VAR *VarVal; // r15
  __int16 v9; // dx
  SAFEARRAY *v10; // rcx
  SAFEARRAY *v11; // rax
  unsigned __int16 *v12; // rbx
  int v13; // ebx
  struct VAR *GcBstrVariant; // rax
  _BYTE v16[8]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *Val; // [rsp+38h] [rbp-8h]
  SAFEARRAY *psa; // [rsp+80h] [rbp+40h] BYREF
  PVOID ppDataToRelease; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 *v20; // [rsp+98h] [rbp+58h] BYREF

  v20 = 0;
  ppDataToRelease = 0;
  *(_WORD *)a1 = 1;
  v3 = a3;
  if ( (unsigned int)(a2 - 1) <= 1 )
  {
    v5 = 2;
    v16[0] = 0;
    Val = 0;
    if ( a2 == 2 )
    {
      Val = VAR::BstrGetVal(a3);
      if ( Val == (unsigned __int16 *)-1LL )
        goto LABEL_30;
      v3 = (struct VAR *)((char *)v3 + 24);
      BSTRHelper::CloneIfNeeded((BSTRHelper *)v16, v3);
      v6 = Val;
      if ( Val )
        v7 = *((_DWORD *)Val - 1);
      else
        v7 = 0;
      v5 = v7 & 0xFFFFFFFE;
    }
    else
    {
      v6 = L" ";
    }
    VarVal = VAR::PvarGetVarVal(v3, 0);
    v9 = *(_WORD *)VarVal;
    if ( *(_WORD *)VarVal != 1 )
    {
      if ( ((v9 - 8204) & 0xBFFF) != 0 )
        goto LABEL_29;
      v10 = (SAFEARRAY *)*((_QWORD *)VarVal + 1);
      psa = v10;
      if ( (v9 & 0x4000) == 0 )
      {
        v11 = v10;
        goto LABEL_15;
      }
      if ( v10 )
      {
        v11 = *(SAFEARRAY **)&v10->cDims;
        v10 = v11;
        psa = v11;
LABEL_15:
        if ( !v11 )
        {
          v12 = _SysAllocStringLen(0, 0);
          if ( !v12 )
          {
LABEL_17:
            v13 = -2146828281;
LABEL_31:
            BSTRHelper::~BSTRHelper((BSTRHelper *)v16);
            return (unsigned int)v13;
          }
LABEL_26:
          *(_WORD *)a1 = 74;
          GcBstrVariant = MakeGcBstrVariant(v12);
          *((_QWORD *)a1 + 1) = GcBstrVariant;
          if ( GcBstrVariant )
          {
            BSTRHelper::~BSTRHelper((BSTRHelper *)v16);
            return 0;
          }
          SysFreeString(v12);
          goto LABEL_17;
        }
        if ( v10->cDims == 1 )
        {
          v13 = SafeArrayAddRef(v10, &ppDataToRelease);
          if ( v13 < 0 )
            goto LABEL_31;
          v13 = rtJoin((__int64)VarVal, &psa, v6, v5, &v20);
          if ( ppDataToRelease )
            SafeArrayReleaseData(ppDataToRelease);
          if ( psa )
            SafeArrayReleaseDescriptor(psa);
          if ( v13 < 0 )
            goto LABEL_31;
          v12 = v20;
          goto LABEL_26;
        }
LABEL_29:
        v13 = -2146828275;
        goto LABEL_31;
      }
    }
LABEL_30:
    v13 = -2146828194;
    goto LABEL_31;
  }
  return 2148139458LL;
}

```

## disassembly

```asm
0x1800266c0  push    rbp
0x1800266c2  push    rbx
0x1800266c3  push    rsi
0x1800266c4  push    rdi
0x1800266c5  push    r13
0x1800266c7  push    r14
0x1800266c9  push    r15
0x1800266cb  mov     rbp, rsp
0x1800266ce  sub     rsp, 40h
0x1800266d2  mov     r13d, 1
0x1800266d8  mov     [rbp+arg_18], 0
0x1800266e0  lea     eax, [rdx-1]
0x1800266e3  mov     [rbp+ppDataToRelease], 0
0x1800266eb  mov     [rcx], r13w
0x1800266ef  mov     rbx, r8
0x1800266f2  mov     r14, rcx
0x1800266f5  cmp     eax, r13d
0x1800266f8  ja      loc_18002689A
0x1800266fe  lea     edi, [r13+1]
0x180026702  mov     [rbp+var_10], 0
0x180026706  mov     [rbp+var_8], 0
0x18002670e  cmp     edx, edi
0x180026710  jnz     short loc_18002674D
0x180026712  mov     rcx, rbx; this
0x180026715  call    ?BstrGetVal@VAR@@QEAAPEAGXZ; VAR::BstrGetVal(void)
0x18002671a  mov     [rbp+var_8], rax
0x18002671e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026722  jz      loc_180026888
0x180026728  add     rbx, 18h
0x18002672c  lea     rcx, [rbp+var_10]; this
0x180026730  mov     rdx, rbx; struct VAR *
0x180026733  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x180026738  mov     rsi, [rbp+var_8]
0x18002673c  test    rsi, rsi
0x18002673f  jnz     short loc_180026745
0x180026741  xor     edi, edi
0x180026743  jmp     short loc_180026748
0x180026745  mov     edi, [rsi-4]
0x180026748  and     edi, 0FFFFFFFEh
0x18002674b  jmp     short loc_180026754
0x18002674d  lea     rsi, asc_1800842F0; " "
0x180026754  xor     edx, edx; int
0x180026756  mov     rcx, rbx; this
0x180026759  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x18002675e  mov     r15, rax
0x180026761  movzx   edx, word ptr [rax]
0x180026764  cmp     r13w, dx
0x180026768  jz      loc_180026888
0x18002676e  mov     eax, 200Ch
0x180026773  movzx   ecx, dx
0x180026776  sub     cx, ax
0x180026779  mov     eax, 0BFFFh
0x18002677e  test    ax, cx
0x180026781  jnz     loc_180026881
0x180026787  mov     rcx, [r15+8]; psa
0x18002678b  mov     eax, 4000h
0x180026790  and     dx, ax
0x180026793  mov     [rbp+psa], rcx
0x180026797  xor     eax, eax
0x180026799  cmp     ax, dx
0x18002679c  jz      short loc_1800267B3
0x18002679e  test    rcx, rcx
0x1800267a1  jz      loc_180026888
0x1800267a7  mov     rax, [rcx]
0x1800267aa  mov     rcx, rax
0x1800267ad  mov     [rbp+psa], rax
0x1800267b1  jmp     short loc_1800267B6
0x1800267b3  mov     rax, rcx
0x1800267b6  test    rax, rax
0x1800267b9  jnz     short loc_1800267D6
0x1800267bb  xor     edx, edx; unsigned int
0x1800267bd  xor     ecx, ecx; unsigned __int16 *
0x1800267bf  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800267c4  mov     rbx, rax
0x1800267c7  test    rax, rax
0x1800267ca  jnz     short loc_180026849
0x1800267cc  mov     ebx, 800A0007h
0x1800267d1  jmp     loc_18002688D
0x1800267d6  cmp     r13w, [rcx]
0x1800267da  jnz     loc_180026881
0x1800267e0  lea     rdx, [rbp+ppDataToRelease]; ppDataToRelease
0x1800267e4  call    cs:__imp_SafeArrayAddRef
0x1800267eb  nop     dword ptr [rax+rax+00h]
0x1800267f0  mov     ebx, eax
0x1800267f2  test    eax, eax
0x1800267f4  js      loc_18002688D
0x1800267fa  lea     rax, [rbp+arg_18]
0x1800267fe  mov     r9d, edi
0x180026801  mov     r8, rsi
0x180026804  mov     [rsp+40h+var_20], rax
0x180026809  lea     rdx, [rbp+psa]
0x18002680d  mov     rcx, r15
0x180026810  call    rtJoin
0x180026815  mov     rcx, [rbp+ppDataToRelease]; pData
0x180026819  mov     ebx, eax
0x18002681b  test    rcx, rcx
0x18002681e  jz      short loc_18002682C
0x180026820  call    cs:__imp_SafeArrayReleaseData
0x180026827  nop     dword ptr [rax+rax+00h]
0x18002682c  mov     rcx, [rbp+psa]; psa
0x180026830  test    rcx, rcx
0x180026833  jz      short loc_180026841
0x180026835  call    cs:__imp_SafeArrayReleaseDescriptor
0x18002683c  nop     dword ptr [rax+rax+00h]
0x180026841  test    ebx, ebx
0x180026843  js      short loc_18002688D
0x180026845  mov     rbx, [rbp+arg_18]
0x180026849  mov     rcx, rbx; unsigned __int16 *
0x18002684c  mov     word ptr [r14], 4Ah ; 'J'
0x180026852  call    ?MakeGcBstrVariant@@YAPEAVVAR@@PEAG@Z; MakeGcBstrVariant(ushort *)
0x180026857  mov     [r14+8], rax
0x18002685b  test    rax, rax
0x18002685e  jnz     short loc_180026874
0x180026860  mov     rcx, rbx; bstrString
0x180026863  call    cs:__imp_SysFreeString
0x18002686a  nop     dword ptr [rax+rax+00h]
0x18002686f  jmp     loc_1800267CC
0x180026874  lea     rcx, [rbp+var_10]; this
0x180026878  call    ??1BSTRHelper@@QEAA@XZ; BSTRHelper::~BSTRHelper(void)
0x18002687d  xor     eax, eax
0x18002687f  jmp     short loc_18002689F
0x180026881  mov     ebx, 800A000Dh
0x180026886  jmp     short loc_18002688D
0x180026888  mov     ebx, 800A005Eh
0x18002688d  lea     rcx, [rbp+var_10]; this
0x180026891  call    ??1BSTRHelper@@QEAA@XZ; BSTRHelper::~BSTRHelper(void)
0x180026896  mov     eax, ebx
0x180026898  jmp     short loc_18002689F
0x18002689a  mov     eax, 800A01C2h
0x18002689f  add     rsp, 40h
0x1800268a3  pop     r15
0x1800268a5  pop     r14
0x1800268a7  pop     r13
0x1800268a9  pop     rdi
0x1800268aa  pop     rsi
0x1800268ab  pop     rbx
0x1800268ac  pop     rbp
0x1800268ad  retn
```
