# CBasicUnloadInstruction::staticRead(IWbemServices *,IWbemContext *,ushort const *)

- ea: `0x180025210`
- end: `0x1800254c9`
- name: `?staticRead@CBasicUnloadInstruction@@SA?AVCWbemInterval@@PEAUIWbemServices@@PEAUIWbemContext@@PEBG@Z`
- size: `697`
- prototype: `static struct CWbemInterval __high(struct IWbemServices *, struct IWbemContext *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180014120`
- `0x180025210`
- `0x1800254d0`
- `0x18004148c`
- `0x180047010`

## import_xrefs

- `msvcrt!swscanf` at `0x1800253ce`
- `msvcrt!swscanf` at `0x1800253ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180025231`
- `OLEAUT32!__imp_SysAllocString` at `0x180025231`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800252e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800252e8`
- `OLEAUT32!__imp_VariantClear` at `0x180025427`
- `OLEAUT32!__imp_VariantClear` at `0x18002548e`
- `OLEAUT32!__imp_VariantClear` at `0x180025427`
- `OLEAUT32!__imp_VariantClear` at `0x18002548e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_DWORD *__fastcall CBasicUnloadInstruction::staticRead(_DWORD *a1, __int64 a2, __int64 a3, const OLECHAR *a4)
{
  OLECHAR *v7; // rax
  OLECHAR *v8; // rsi
  int v9; // eax
  char v10; // bl
  int v11; // r8d
  __int64 v12; // rbx
  int v13; // eax
  char v14; // r14
  int v15; // r8d
  int v16; // r8d
  int v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+44h] [rbp-25h] BYREF
  int v20; // [rsp+48h] [rbp-21h] BYREF
  int v21; // [rsp+4Ch] [rbp-1Dh] BYREF
  int v22; // [rsp+50h] [rbp-19h] BYREF
  int v23; // [rsp+54h] [rbp-15h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+78h] [rbp+Fh]
  OLECHAR *v27[8]; // [rsp+80h] [rbp+17h] BYREF

  v7 = SysAllocString(a4);
  v8 = v7;
  if ( !v7 )
  {
    *a1 = -1;
    return a1;
  }
  v27[0] = v7;
  v24 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int64, __int64 *, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         v7,
         0,
         a3,
         &v24,
         0);
  v10 = v9;
  if ( v9 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (_DWORD)v8, v10);
    }
    *a1 = -1;
LABEL_32:
    SysFreeString(v8);
    return a1;
  }
  v12 = v24;
  v26 = v24;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v24 + 32LL))(
          v24,
          L"ClearAfter",
          0,
          &pvarg,
          0,
          0);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v27[1] = (OLECHAR *)&pvarg;
    if ( pvarg.vt == 8 )
    {
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v18 = 0;
      if ( swscanf(pvarg.bstrVal, L"%4u%2u%2u%2u%2u%2u", &v19, &v20, &v21, &v22, &v23, &v18) == 6 )
      {
        if ( v19 || v20 )
        {
          *a1 = -1;
        }
        else
        {
          v18 += 60 * (v23 + 60 * (v22 + 24 * v21));
          *a1 = 1000 * v18;
        }
        VariantClear(&pvarg);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v26 = 0;
        goto LABEL_32;
      }
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0xFFFFFFFF);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v16, (_DWORD)v8, v14);
      }
    }
    *a1 = -1;
    VariantClear(&pvarg);
  }
  else
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v15, (_DWORD)v8, v14);
    }
    *a1 = -1;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v26 = 0;
  CSysFreeMe::~CSysFreeMe(v27);
  return a1;
}

```

## disassembly

```asm
0x180025210  push    rbp
0x180025212  push    rbx
0x180025213  push    rsi
0x180025214  push    rdi
0x180025215  push    r14
0x180025217  push    r15
0x180025219  lea     rbp, [rsp-2Fh]
0x18002521e  sub     rsp, 98h
0x180025225  mov     r14, r8
0x180025228  mov     rbx, rdx
0x18002522b  mov     rdi, rcx
0x18002522e  mov     rcx, r9; psz
0x180025231  call    cs:__imp_SysAllocString
0x180025237  mov     rsi, rax
0x18002523a  xor     r15d, r15d
0x18002523d  test    rax, rax
0x180025240  jnz     short loc_18002524D
0x180025242  mov     dword ptr [rdi], 0FFFFFFFFh
0x180025248  jmp     loc_1800254B6
0x18002524d  mov     [rbp+57h+var_40], rsi
0x180025251  mov     [rbp+57h+var_68], r15
0x180025255  mov     rax, [rbx]
0x180025258  mov     [rsp+0C0h+var_98], r15
0x18002525d  lea     rcx, [rbp+57h+var_68]
0x180025261  mov     [rsp+0C0h+var_A0], rcx
0x180025266  mov     r9, r14
0x180025269  xor     r8d, r8d
0x18002526c  mov     rdx, rsi
0x18002526f  mov     rcx, rbx
0x180025272  mov     rax, [rax+30h]
0x180025276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002527b  mov     ebx, eax
0x18002527d  test    eax, eax
0x18002527f  jns     short loc_1800252CF
0x180025281  or      edx, 0FFFFFFFFh; int
0x180025284  lea     rcx, qword_18006A9C0; this
0x18002528b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025290  lea     rdx, WPP_GLOBAL_Control
0x180025297  mov     rcx, cs:WPP_GLOBAL_Control
0x18002529e  cmp     rcx, rdx
0x1800252a1  jz      short loc_1800252C4
0x1800252a3  test    byte ptr [rcx+1Ch], 1
0x1800252a7  jz      short loc_1800252C4
0x1800252a9  cmp     byte ptr [rcx+19h], 2
0x1800252ad  jb      short loc_1800252C4
0x1800252af  mov     edx, 0Ah
0x1800252b4  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800252b8  mov     r9, rsi
0x1800252bb  mov     rcx, [rcx+10h]
0x1800252bf  call    WPP_SF_SD
0x1800252c4  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800252ca  jmp     loc_1800254AD
0x1800252cf  mov     rbx, [rbp+57h+var_68]
0x1800252d3  mov     [rbp+57h+var_48], rbx
0x1800252d7  xorps   xmm0, xmm0
0x1800252da  xor     eax, eax
0x1800252dc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800252e0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800252e4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800252e8  call    cs:__imp_VariantInit
0x1800252ee  mov     rcx, [rbp+57h+var_68]
0x1800252f2  mov     rax, [rcx]
0x1800252f5  mov     [rsp+0C0h+var_98], r15
0x1800252fa  mov     [rsp+0C0h+var_A0], r15
0x1800252ff  lea     r9, [rbp+57h+pvarg]
0x180025303  xor     r8d, r8d
0x180025306  lea     rdx, aClearafter; "ClearAfter"
0x18002530d  mov     rax, [rax+20h]
0x180025311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025316  mov     r14d, eax
0x180025319  test    eax, eax
0x18002531b  jns     short loc_18002536C
0x18002531d  or      edx, 0FFFFFFFFh; int
0x180025320  lea     rcx, qword_18006A9C0; this
0x180025327  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002532c  lea     rdx, WPP_GLOBAL_Control
0x180025333  mov     rcx, cs:WPP_GLOBAL_Control
0x18002533a  cmp     rcx, rdx
0x18002533d  jz      short loc_180025361
0x18002533f  test    byte ptr [rcx+1Ch], 1
0x180025343  jz      short loc_180025361
0x180025345  cmp     byte ptr [rcx+19h], 2
0x180025349  jb      short loc_180025361
0x18002534b  mov     edx, 0Bh
0x180025350  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180025355  mov     r9, rsi
0x180025358  mov     rcx, [rcx+10h]
0x18002535c  call    WPP_SF_SD
0x180025361  mov     dword ptr [rdi], 0FFFFFFFFh
0x180025367  jmp     loc_18002542E
0x18002536c  lea     rax, [rbp+57h+pvarg]
0x180025370  mov     [rbp+57h+var_38], rax
0x180025374  cmp     word ptr [rbp+57h+pvarg], 8
0x180025379  jnz     loc_18002541D
0x18002537f  mov     [rbp+57h+var_7C], r15d
0x180025383  mov     [rbp+57h+var_78], r15d
0x180025387  mov     [rbp+57h+var_74], r15d
0x18002538b  mov     [rbp+57h+var_70], r15d
0x18002538f  mov     [rbp+57h+var_6C], r15d
0x180025393  mov     [rbp+57h+var_80], r15d
0x180025397  lea     rax, [rbp+57h+var_80]
0x18002539b  mov     [rsp+0C0h+var_88], rax
0x1800253a0  lea     rax, [rbp+57h+var_6C]
0x1800253a4  mov     [rsp+0C0h+var_90], rax
0x1800253a9  lea     rax, [rbp+57h+var_70]
0x1800253ad  mov     [rsp+0C0h+var_98], rax
0x1800253b2  lea     rax, [rbp+57h+var_74]
0x1800253b6  mov     [rsp+0C0h+var_A0], rax
0x1800253bb  lea     r9, [rbp+57h+var_78]
0x1800253bf  lea     r8, [rbp+57h+var_7C]
0x1800253c3  lea     rdx, a4u2u2u2u2u2u; "%4u%2u%2u%2u%2u%2u"
0x1800253ca  mov     rcx, qword ptr [rbp+57h+pvarg+8]; Buffer
0x1800253ce  call    cs:__imp_swscanf
0x1800253d4  cmp     eax, 6
0x1800253d7  jz      short loc_180025451
0x1800253d9  or      edx, 0FFFFFFFFh; int
0x1800253dc  lea     rcx, qword_18006A9C0; this
0x1800253e3  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800253e8  lea     rdx, WPP_GLOBAL_Control
0x1800253ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253f6  cmp     rcx, rdx
0x1800253f9  jz      short loc_18002541D
0x1800253fb  test    byte ptr [rcx+1Ch], 1
0x1800253ff  jz      short loc_18002541D
0x180025401  cmp     byte ptr [rcx+19h], 2
0x180025405  jb      short loc_18002541D
0x180025407  mov     edx, 0Ch
0x18002540c  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180025411  mov     r9, rsi
0x180025414  mov     rcx, [rcx+10h]
0x180025418  call    WPP_SF_SD
0x18002541d  mov     dword ptr [rdi], 0FFFFFFFFh
0x180025423  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180025427  call    cs:__imp_VariantClear
0x18002542d  nop
0x18002542e  test    rbx, rbx
0x180025431  jz      short loc_180025442
0x180025433  mov     rax, [rbx]
0x180025436  mov     rcx, rbx
0x180025439  mov     rax, [rax+10h]
0x18002543d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025442  mov     [rbp+57h+var_48], r15
0x180025446  lea     rcx, [rbp+57h+var_40]; this
0x18002544a  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18002544f  jmp     short loc_1800254B6
0x180025451  cmp     [rbp+57h+var_7C], r15d
0x180025455  jnz     short loc_180025484
0x180025457  cmp     [rbp+57h+var_78], r15d
0x18002545b  jnz     short loc_180025484
0x18002545d  mov     eax, [rbp+57h+var_74]
0x180025460  lea     ecx, [rax+rax*2]
0x180025463  mov     eax, [rbp+57h+var_70]
0x180025466  lea     ecx, [rax+rcx*8]
0x180025469  imul    eax, ecx, 3Ch ; '<'
0x18002546c  add     eax, [rbp+57h+var_6C]
0x18002546f  imul    ecx, eax, 3Ch ; '<'
0x180025472  mov     eax, [rbp+57h+var_80]
0x180025475  add     eax, ecx
0x180025477  mov     [rbp+57h+var_80], eax
0x18002547a  imul    eax, 3E8h
0x180025480  mov     [rdi], eax
0x180025482  jmp     short loc_18002548A
0x180025484  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002548a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002548e  call    cs:__imp_VariantClear
0x180025494  nop
0x180025495  test    rbx, rbx
0x180025498  jz      short loc_1800254A9
0x18002549a  mov     rax, [rbx]
0x18002549d  mov     rcx, rbx
0x1800254a0  mov     rax, [rax+10h]
0x1800254a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254a9  mov     [rbp+57h+var_48], r15
0x1800254ad  mov     rcx, rsi; bstrString
0x1800254b0  call    cs:__imp_SysFreeString
0x1800254b6  mov     rax, rdi
0x1800254b9  add     rsp, 98h
0x1800254c0  pop     r15
0x1800254c2  pop     r14
0x1800254c4  pop     rdi
0x1800254c5  pop     rsi
0x1800254c6  pop     rbx
0x1800254c7  pop     rbp
0x1800254c8  retn
```
