# GetShellPath(_UserProfileData *,ushort const *,ushort * *)

- ea: `0x180018f6c`
- end: `0x1800190b3`
- name: `?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct _UserProfileData *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180010980`
- `0x180010b4c`
- `0x180011224`

## callees

- `0x180014fd0`
- `0x18001586c`
- `0x180015974`
- `0x180015f34`
- `0x180018f6c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019006`
- `msvcrt!_wcsicmp` at `0x180019006`

## string_xrefs

- `0x180018f89`: `GetShellPath`

## pseudocode

```c
__int64 __fastcall GetShellPath(struct _UserProfileData *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int16 v6; // ax
  unsigned int v7; // r12d
  unsigned int v8; // ebx
  __int64 v9; // r13
  int v10; // ebx
  int v12; // [rsp+30h] [rbp-48h] BYREF
  __int16 v13; // [rsp+34h] [rbp-44h]
  __int16 v14; // [rsp+36h] [rbp-42h]
  unsigned __int16 *v15; // [rsp+C0h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "GetShellPath", 639, 1);
  v6 = 641;
  if ( !a1 || (v13 = 641, v6 = 642, !a2) || (v13 = 642, v6 = 643, !a3) )
  {
    v10 = -2147024809;
LABEL_15:
    v12 = v10;
LABEL_16:
    v14 = v6;
    goto LABEL_17;
  }
  v7 = *((_DWORD *)a1 + 14);
  v8 = 0;
  v9 = *((_QWORD *)a1 + 6);
  v12 = 0;
  v13 = 643;
  v15 = 0;
  if ( !v7 )
    goto LABEL_7;
  while ( _wcsicmp(*(const wchar_t **)(v9 + 16LL * v8), a2) )
  {
    if ( ++v8 >= v7 )
      goto LABEL_7;
  }
  v10 = SdSafeDuplicateStr(&v15, *(const unsigned __int16 **)(v9 + 16LL * v8 + 8));
  v12 = v10;
  v6 = 653;
  if ( v10 < 0 )
    goto LABEL_16;
  v13 = 653;
  if ( !v15 )
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids,
        (_DWORD)a2,
        *((_QWORD *)a1 + 2));
    v10 = -2130706376;
    v6 = 661;
    goto LABEL_15;
  }
  *a3 = v15;
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018f6c  push    rbp
0x180018f6e  push    rbx
0x180018f6f  push    rsi
0x180018f70  push    rdi
0x180018f71  push    r12
0x180018f73  push    r13
0x180018f75  push    r14
0x180018f77  push    r15
0x180018f79  mov     rbp, rsp
0x180018f7c  sub     rsp, 78h
0x180018f80  mov     r14, r8
0x180018f83  mov     r15, rdx
0x180018f86  mov     rdi, rcx
0x180018f89  lea     rdx, aGetshellpath; "GetShellPath"
0x180018f90  mov     r8d, 27Fh; unsigned __int16
0x180018f96  lea     rcx, [rbp+var_48]; this
0x180018f9a  mov     r9d, 1; unsigned __int16
0x180018fa0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018fa5  mov     eax, 281h
0x180018faa  test    rdi, rdi
0x180018fad  jz      loc_18001908B
0x180018fb3  mov     [rbp+var_44], ax
0x180018fb7  mov     eax, 282h
0x180018fbc  test    r15, r15
0x180018fbf  jz      loc_18001908B
0x180018fc5  mov     [rbp+var_44], ax
0x180018fc9  mov     eax, 283h
0x180018fce  test    r14, r14
0x180018fd1  jz      loc_18001908B
0x180018fd7  mov     r12d, [rdi+38h]
0x180018fdb  xor     ebx, ebx
0x180018fdd  mov     r13, [rdi+30h]
0x180018fe1  mov     [rbp+var_48], 0
0x180018fe8  mov     [rbp+var_44], ax
0x180018fec  mov     [rbp+arg_0], 0
0x180018ff4  test    r12d, r12d
0x180018ff7  jz      short loc_180019017
0x180018ff9  mov     esi, ebx
0x180018ffb  mov     rdx, r15; String2
0x180018ffe  add     rsi, rsi
0x180019001  mov     rcx, [r13+rsi*8+0]; String1
0x180019006  call    cs:__imp__wcsicmp
0x18001900c  test    eax, eax
0x18001900e  jz      short loc_18001905D
0x180019010  inc     ebx
0x180019012  cmp     ebx, r12d
0x180019015  jb      short loc_180018FF9
0x180019017  mov     rcx, cs:WPP_GLOBAL_Control
0x18001901e  lea     rax, WPP_GLOBAL_Control
0x180019025  cmp     rcx, rax
0x180019028  jz      short loc_180019051
0x18001902a  test    byte ptr [rcx+1Ch], 40h
0x18001902e  jz      short loc_180019051
0x180019030  mov     rax, [rdi+10h]
0x180019034  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18001903b  mov     rcx, [rcx+10h]
0x18001903f  mov     edx, 1Ah
0x180019044  mov     r9, r15
0x180019047  mov     [rsp+78h+var_58], rax
0x18001904c  call    WPP_SF_SS
0x180019051  mov     ebx, 81000038h
0x180019056  mov     eax, 295h
0x18001905b  jmp     short loc_180019090
0x18001905d  mov     rdx, [r13+rsi*8+8]; unsigned __int16 *
0x180019062  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x180019066  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18001906b  mov     ebx, eax
0x18001906d  mov     [rbp+var_48], eax
0x180019070  test    eax, eax
0x180019072  mov     eax, 28Dh
0x180019077  js      short loc_180019093
0x180019079  mov     [rbp+var_44], ax
0x18001907d  mov     rax, [rbp+arg_0]
0x180019081  test    rax, rax
0x180019084  jz      short loc_180019017
0x180019086  mov     [r14], rax
0x180019089  jmp     short loc_180019097
0x18001908b  mov     ebx, 80070057h
0x180019090  mov     [rbp+var_48], ebx
0x180019093  mov     [rbp+var_42], ax
0x180019097  lea     rcx, [rbp+var_48]; this
0x18001909b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800190a0  mov     eax, ebx
0x1800190a2  add     rsp, 78h
0x1800190a6  pop     r15
0x1800190a8  pop     r14
0x1800190aa  pop     r13
0x1800190ac  pop     r12
0x1800190ae  pop     rdi
0x1800190af  pop     rsi
0x1800190b0  pop     rbx
0x1800190b1  pop     rbp
0x1800190b2  retn
```
