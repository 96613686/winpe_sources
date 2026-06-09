# SdpParamSetToSafeArrays(_SDIAG_PARAMSET *,tagSAFEARRAY * *,tagSAFEARRAY * *)

- ea: `0x180005590`
- end: `0x180005713`
- name: `?SdpParamSetToSafeArrays@@YAJPEAU_SDIAG_PARAMSET@@PEAPEAUtagSAFEARRAY@@1@Z`
- size: `387`
- prototype: `__int64 __fastcall(struct _SDIAG_PARAMSET *, struct tagSAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e194`

## callees

- `0x180005590`
- `0x180026fa0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800056fd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000570b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800056fd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000570b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180005679`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800056a0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180005679`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800056a0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180005611`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180005633`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180005611`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180005633`

## pseudocode

```c
__int64 __fastcall SdpParamSetToSafeArrays(
        struct _SDIAG_PARAMSET *a1,
        struct tagSAFEARRAY **a2,
        struct tagSAFEARRAY **a3)
{
  unsigned int v6; // r8d
  int v7; // r9d
  unsigned int v8; // edi
  SAFEARRAY *Vector; // r14
  SAFEARRAY *v10; // rbp
  int v11; // r9d
  unsigned int v12; // r8d
  __int64 v13; // rax
  HRESULT v14; // eax
  LONG rgIndices; // [rsp+50h] [rbp+8h] BYREF

  rgIndices = 0;
  if ( !a1 )
  {
    v6 = 55;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    v8 = v7;
    SdpDebugTrace(1u, L"SdpParamSetToSafeArrays", v6, v7);
    return v8;
  }
  if ( !*(_QWORD *)a1 )
  {
    v6 = 56;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v6 = 57;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 58;
    goto LABEL_3;
  }
  Vector = SafeArrayCreateVector(8u, 0, *((_DWORD *)a1 + 2));
  if ( !Vector )
  {
    v7 = -2147024882;
    v6 = 61;
    goto LABEL_4;
  }
  v10 = SafeArrayCreateVector(8u, 0, *((_DWORD *)a1 + 2));
  if ( v10 )
  {
    v8 = 0;
    rgIndices = 0;
    if ( !*((_DWORD *)a1 + 2) )
    {
LABEL_20:
      *a2 = Vector;
      *a3 = v10;
      return v8;
    }
    v13 = 0;
    while ( 1 )
    {
      v8 = SafeArrayPutElement(Vector, &rgIndices, *(void **)(*(_QWORD *)a1 + 24 * v13));
      v11 = v8;
      if ( (v8 & 0x80000000) != 0 )
        break;
      v14 = SafeArrayPutElement(v10, &rgIndices, *(void **)(*(_QWORD *)a1 + 24LL * (unsigned int)rgIndices + 8));
      v8 = v14;
      if ( v14 < 0 )
      {
        v12 = 75;
        v11 = v14;
        goto LABEL_24;
      }
      v13 = (unsigned int)(rgIndices + 1);
      rgIndices = v13;
      if ( (unsigned int)v13 >= *((_DWORD *)a1 + 2) )
        goto LABEL_20;
    }
    v12 = 70;
  }
  else
  {
    v11 = -2147024882;
    v8 = -2147024882;
    v12 = 64;
  }
LABEL_24:
  SdpDebugTrace(1u, L"SdpParamSetToSafeArrays", v12, v11);
  SafeArrayDestroy(Vector);
  if ( v10 )
    SafeArrayDestroy(v10);
  return v8;
}

```

## disassembly

```asm
0x180005590  mov     [rsp+arg_8], rbx
0x180005595  mov     [rsp+arg_10], rbp
0x18000559a  push    rsi
0x18000559b  push    rdi
0x18000559c  push    r12
0x18000559e  push    r14
0x1800055a0  push    r15
0x1800055a2  sub     rsp, 20h
0x1800055a6  mov     [rsp+48h+rgIndices], 0
0x1800055ae  mov     r15, r8
0x1800055b1  mov     r12, rdx
0x1800055b4  mov     rsi, rcx
0x1800055b7  test    rcx, rcx
0x1800055ba  jnz     short loc_1800055DF
0x1800055bc  lea     r8d, [rcx+37h]; int
0x1800055c0  mov     r9d, 80070057h; int
0x1800055c6  lea     rdx, aSdpparamsettos; "SdpParamSetToSafeArrays"
0x1800055cd  mov     ecx, 1; Level
0x1800055d2  mov     edi, r9d
0x1800055d5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800055da  jmp     loc_1800056C2
0x1800055df  cmp     qword ptr [rcx], 0
0x1800055e3  jnz     short loc_1800055ED
0x1800055e5  mov     r8d, 38h ; '8'
0x1800055eb  jmp     short loc_1800055C0
0x1800055ed  test    r12, r12
0x1800055f0  jnz     short loc_1800055F9
0x1800055f2  lea     r8d, [r12+39h]
0x1800055f7  jmp     short loc_1800055C0
0x1800055f9  test    r15, r15
0x1800055fc  jnz     short loc_180005604
0x1800055fe  lea     r8d, [r15+3Ah]
0x180005602  jmp     short loc_1800055C0
0x180005604  mov     r8d, [rsi+8]; cElements
0x180005608  mov     ebx, 8
0x18000560d  mov     ecx, ebx; vt
0x18000560f  xor     edx, edx; lLbound
0x180005611  call    cs:__imp_SafeArrayCreateVector
0x180005617  mov     r14, rax
0x18000561a  test    rax, rax
0x18000561d  jnz     short loc_18000562B
0x18000561f  mov     r9d, 8007000Eh
0x180005625  lea     r8d, [rbx+35h]
0x180005629  jmp     short loc_1800055C6
0x18000562b  mov     r8d, [rsi+8]; cElements
0x18000562f  mov     ecx, ebx; vt
0x180005631  xor     edx, edx; lLbound
0x180005633  call    cs:__imp_SafeArrayCreateVector
0x180005639  mov     rbp, rax
0x18000563c  test    rax, rax
0x18000563f  jnz     short loc_180005656
0x180005641  mov     r9d, 8007000Eh
0x180005647  lea     ebx, [rax+1]
0x18000564a  mov     edi, r9d
0x18000564d  lea     r8d, [rax+40h]
0x180005651  jmp     loc_1800056EC
0x180005656  xor     edi, edi
0x180005658  mov     [rsp+48h+rgIndices], edi
0x18000565c  cmp     [rsi+8], edi
0x18000565f  jbe     short loc_1800056BB
0x180005661  xor     eax, eax
0x180005663  lea     ebx, [rdi+1]
0x180005666  mov     r8, [rsi]
0x180005669  lea     rcx, [rax+rax*2]
0x18000566d  lea     rdx, [rsp+48h+rgIndices]; rgIndices
0x180005672  mov     r8, [r8+rcx*8]; pv
0x180005676  mov     rcx, r14; psa
0x180005679  call    cs:__imp_SafeArrayPutElement
0x18000567f  mov     edi, eax
0x180005681  mov     r9d, eax; int
0x180005684  test    eax, eax
0x180005686  js      short loc_1800056E6
0x180005688  mov     eax, [rsp+48h+rgIndices]
0x18000568c  lea     rdx, [rsp+48h+rgIndices]; rgIndices
0x180005691  mov     r8, [rsi]
0x180005694  lea     rcx, [rax+rax*2]
0x180005698  mov     r8, [r8+rcx*8+8]; pv
0x18000569d  mov     rcx, rbp; psa
0x1800056a0  call    cs:__imp_SafeArrayPutElement
0x1800056a6  mov     edi, eax
0x1800056a8  test    eax, eax
0x1800056aa  js      short loc_1800056DB
0x1800056ac  mov     eax, [rsp+48h+rgIndices]
0x1800056b0  add     eax, ebx
0x1800056b2  mov     [rsp+48h+rgIndices], eax
0x1800056b6  cmp     eax, [rsi+8]
0x1800056b9  jb      short loc_180005666
0x1800056bb  mov     [r12], r14
0x1800056bf  mov     [r15], rbp
0x1800056c2  mov     rbx, [rsp+48h+arg_8]
0x1800056c7  mov     eax, edi
0x1800056c9  mov     rbp, [rsp+48h+arg_10]
0x1800056ce  add     rsp, 20h
0x1800056d2  pop     r15
0x1800056d4  pop     r14
0x1800056d6  pop     r12
0x1800056d8  pop     rdi
0x1800056d9  pop     rsi
0x1800056da  retn
0x1800056db  mov     r8d, 4Bh ; 'K'
0x1800056e1  mov     r9d, eax
0x1800056e4  jmp     short loc_1800056EC
0x1800056e6  mov     r8d, 46h ; 'F'; int
0x1800056ec  lea     rdx, aSdpparamsettos; "SdpParamSetToSafeArrays"
0x1800056f3  mov     ecx, ebx; Level
0x1800056f5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800056fa  mov     rcx, r14; psa
0x1800056fd  call    cs:__imp_SafeArrayDestroy
0x180005703  test    rbp, rbp
0x180005706  jz      short loc_1800056C2
0x180005708  mov     rcx, rbp; psa
0x18000570b  call    cs:__imp_SafeArrayDestroy
0x180005711  jmp     short loc_1800056C2
```
