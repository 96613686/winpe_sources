# CGlobalStore::StartGlobalTraceLoggingActivity(WinLogonActivityType)

- ea: `0x1400190c0`
- end: `0x14001937f`
- name: `?StartGlobalTraceLoggingActivity@CGlobalStore@@QEAAJW4WinLogonActivityType@@@Z`
- size: `703`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011490`
- `0x140015ba0`
- `0x140018e10`

## callees

- `0x14000aa04`
- `0x1400190c0`
- `0x140053398`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019317`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001934b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019317`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001934b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400190ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400190ed`
- `ntdll!EtwEventActivityIdControl` at `0x1400191b6`
- `ntdll!EtwEventActivityIdControl` at `0x1400191b6`
- `ntdll!EtwEventWriteTransfer` at `0x1400192f9`
- `ntdll!EtwEventWriteTransfer` at `0x1400192f9`

## string_xrefs

- `0x140019101`: `clientcore\ds\security\umstartup\winlogon\core\globalstore.cxx`
- `0x140019325`: `clientcore\ds\security\umstartup\winlogon\core\globalstore.cxx`

## pseudocode

```c
__int64 __fastcall CGlobalStore::StartGlobalTraceLoggingActivity(RTL_SRWLOCK *a1, char a2)
{
  RTL_SRWLOCK *v2; // rdi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // r15
  _DWORD *Ptr; // rax
  int v10; // eax
  char *v11; // r9
  int v12; // [rsp+20h] [rbp-69h]
  __int64 v13; // [rsp+30h] [rbp-59h] BYREF
  __int64 v14; // [rsp+38h] [rbp-51h]
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v16[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h]
  char *v18; // [rsp+60h] [rbp-29h] BYREF
  int v19; // [rsp+68h] [rbp-21h]
  int v20; // [rsp+6Ch] [rbp-1Dh]
  __int16 *v21; // [rsp+70h] [rbp-19h]
  __int64 v22; // [rsp+78h] [rbp-11h]
  __int64 *v23; // [rsp+80h] [rbp-9h]
  __int64 v24; // [rsp+88h] [rbp-1h]
  char *v25; // [rsp+90h] [rbp+7h]
  __int64 v26; // [rsp+98h] [rbp+Fh]
  __int64 *v27; // [rsp+A0h] [rbp+17h]
  __int64 v28; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = a1 + 8;
  AcquireSRWLockExclusive(a1 + 8);
  if ( a1[41].Ptr )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x637,
      (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\globalstore.cxx",
      (const char *)0x8000FFFFLL,
      v12);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 2147549183LL;
  }
  else
  {
    v6 = (char *)operator new(0x28u);
    v7 = v6;
    if ( v6 )
    {
      *(_DWORD *)v6 = 0;
      v6[4] = 0;
      a1[41].Ptr = v6;
      if ( (unsigned int)dword_1400CF778 > 5
        && (qword_1400CF788 & 0x400000000000LL) != 0
        && (qword_1400CF790 & 0x400000000000LL) == qword_1400CF790 )
      {
        v8 = v6 + 8;
        EtwEventActivityIdControl(3, v6 + 8);
      }
      else
      {
        v8 = v6 + 8;
        *(_OWORD *)(v6 + 8) = 0;
      }
      *(_DWORD *)v7 = 1;
      if ( (unsigned int)dword_1400CF778 > 5
        && (qword_1400CF788 & 0x400000000000LL) != 0
        && (qword_1400CF790 & 0x400000000000LL) == qword_1400CF790 )
      {
        Ptr = a1[40].Ptr;
        LOBYTE(v13) = a2;
        if ( Ptr )
          v10 = Ptr[22];
        else
          v10 = -1;
        HIDWORD(v13) = v10;
        v15 = 0x1000000;
        if ( !v7[4]
          || (v11 = v7 + 24, !*((_DWORD *)v7 + 6))
          && !*((_DWORD *)v7 + 7)
          && !*((_DWORD *)v7 + 8)
          && !*((_DWORD *)v7 + 9) )
        {
          v11 = 0;
        }
        v28 = 1;
        v27 = &v13;
        v26 = 4;
        v25 = (char *)&v13 + 4;
        v24 = 8;
        v23 = &v15;
        v16[1] = 261;
        v18 = (char *)off_1400CF780;
        v16[0] = 184549376;
        v17 = 0x400000000000LL;
        v19 = *(unsigned __int16 *)off_1400CF780;
        v21 = word_1400BAE82;
        v20 = 2;
        v22 = 0x10000004ALL;
        LODWORD(v14) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        ((void (__fastcall *)(__int64, _DWORD *, char *, char *, int, char **, __int64, __int64, __int64))EtwEventWriteTransfer)(
          qword_1400CF798,
          v16,
          v8,
          v11,
          5,
          &v18,
          v13,
          v14,
          v15);
      }
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      return 0;
    }
    else
    {
      a1[41].Ptr = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x639,
        (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\globalstore.cxx",
        (const char *)0x8007000ELL,
        v12);
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x1400190c0  push    rbp
0x1400190c2  push    rsi
0x1400190c3  push    rdi
0x1400190c4  push    r12
0x1400190c6  lea     rbp, [rsp-3Fh]
0x1400190cb  sub     rsp, 0C8h
0x1400190d2  mov     rax, cs:__security_cookie
0x1400190d9  xor     rax, rsp
0x1400190dc  mov     [rbp+57h+var_30], rax
0x1400190e0  lea     rdi, [rcx+40h]
0x1400190e4  mov     rsi, rcx
0x1400190e7  mov     rcx, rdi; SRWLock
0x1400190ea  mov     r12d, edx
0x1400190ed  call    cs:__imp_AcquireSRWLockExclusive
0x1400190f3  cmp     qword ptr [rsi+148h], 0
0x1400190fb  jz      short loc_140019130
0x1400190fd  mov     rcx, [rbp+5Fh]; this
0x140019101  lea     r8, aClientcoreDsSe_3; "clientcore\\ds\\security\\umstartup\\wi"...
0x140019108  mov     r9d, 8000FFFFh; char *
0x14001910e  mov     edx, 637h; void *
0x140019113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019118  test    rdi, rdi
0x14001911b  jz      short loc_140019126
0x14001911d  mov     rcx, rdi; SRWLock
0x140019120  call    cs:__imp_ReleaseSRWLockExclusive
0x140019126  mov     eax, 8000FFFFh
0x14001912b  jmp     loc_140019366
0x140019130  mov     [rsp+0E0h+arg_8], rbx
0x140019138  mov     ecx, 28h ; '('; Size
0x14001913d  mov     [rsp+0E0h+arg_18], r14
0x140019145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001914a  xor     r14d, r14d
0x14001914d  mov     rbx, rax
0x140019150  test    rax, rax
0x140019153  jz      loc_140019321
0x140019159  mov     [rax], r14d
0x14001915c  mov     [rax+4], r14b
0x140019160  mov     [rsp+0E0h+arg_10], r13
0x140019168  mov     r13, 400000000000h
0x140019172  mov     [rsi+148h], rax
0x140019179  mov     ecx, cs:dword_1400CF778
0x14001917f  mov     [rsp+0E0h+var_20], r15
0x140019187  cmp     ecx, 5
0x14001918a  jbe     short loc_1400191BE
0x14001918c  mov     rdx, cs:qword_1400CF790
0x140019193  mov     rcx, cs:qword_1400CF788
0x14001919a  test    r13, rcx
0x14001919d  jz      short loc_1400191BE
0x14001919f  mov     rax, rdx
0x1400191a2  and     rax, r13
0x1400191a5  cmp     rax, rdx
0x1400191a8  jnz     short loc_1400191BE
0x1400191aa  lea     r15, [rbx+8]
0x1400191ae  mov     ecx, 3
0x1400191b3  mov     rdx, r15
0x1400191b6  call    cs:__imp_EtwEventActivityIdControl
0x1400191bc  jmp     short loc_1400191C9
0x1400191be  lea     r15, [rbx+8]
0x1400191c2  xorps   xmm0, xmm0
0x1400191c5  movups  xmmword ptr [r15], xmm0
0x1400191c9  mov     dword ptr [rbx], 1
0x1400191cf  mov     eax, cs:dword_1400CF778
0x1400191d5  cmp     eax, 5
0x1400191d8  jbe     loc_1400192FF
0x1400191de  mov     rcx, cs:qword_1400CF790
0x1400191e5  mov     rax, cs:qword_1400CF788
0x1400191ec  test    r13, rax
0x1400191ef  jz      loc_1400192FF
0x1400191f5  mov     rax, rcx
0x1400191f8  and     rax, r13
0x1400191fb  cmp     rax, rcx
0x1400191fe  jnz     loc_1400192FF
0x140019204  mov     rax, [rsi+140h]
0x14001920b  mov     [rbp+57h+var_B0], r12b
0x14001920f  test    rax, rax
0x140019212  jz      short loc_140019219
0x140019214  mov     eax, [rax+58h]
0x140019217  jmp     short loc_14001921E
0x140019219  mov     eax, 0FFFFFFFFh
0x14001921e  mov     [rbp+57h+var_AC], eax
0x140019221  mov     [rbp+57h+var_A0], 1000000h
0x140019229  cmp     [rbx+4], r14b
0x14001922d  jz      short loc_14001924B
0x14001922f  cmp     [rbx+18h], r14d
0x140019233  lea     r9, [rbx+18h]
0x140019237  jnz     short loc_14001924E
0x140019239  cmp     [r9+4], r14d
0x14001923d  jnz     short loc_14001924E
0x14001923f  cmp     [r9+8], r14d
0x140019243  jnz     short loc_14001924E
0x140019245  cmp     [r9+0Ch], r14d
0x140019249  jnz     short loc_14001924E
0x14001924b  mov     r9, r14
0x14001924e  mov     [rbp+57h+var_38], 1
0x140019256  lea     rax, [rbp+57h+var_B0]
0x14001925a  mov     [rbp+57h+var_40], rax
0x14001925e  lea     rcx, _TraceLoggingMetadata
0x140019265  mov     [rbp+57h+var_48], 4
0x14001926d  lea     rax, [rbp+57h+var_AC]
0x140019271  mov     [rbp+57h+var_50], rax
0x140019275  lea     rdx, [rbp+57h+var_98]
0x140019279  lea     rax, [rbp+57h+var_A0]
0x14001927d  mov     [rbp+57h+var_58], 8
0x140019285  mov     [rbp+57h+var_60], rax
0x140019289  mov     r8, r15
0x14001928c  movzx   eax, cs:word_1400BAE78
0x140019293  mov     [rbp+57h+var_94], eax
0x140019296  mov     rax, cs:off_1400CF780
0x14001929d  mov     [rbp+57h+var_80], rax
0x1400192a1  mov     [rbp+57h+var_98], 0B000000h
0x1400192a8  mov     [rbp+57h+var_90], r13
0x1400192ac  movzx   eax, word ptr [rax]
0x1400192af  mov     [rbp+57h+var_78], eax
0x1400192b2  lea     rax, word_1400BAE82
0x1400192b9  mov     [rbp+57h+var_70], rax
0x1400192bd  lea     rax, _TraceLoggingMetadataEnd
0x1400192c4  sub     eax, ecx
0x1400192c6  mov     [rbp+57h+var_74], 2
0x1400192cd  mov     dword ptr [rbp+57h+var_68], 4Ah ; 'J'
0x1400192d4  mov     dword ptr [rbp+57h+var_68+4], 1
0x1400192db  mov     dword ptr [rbp+57h+var_A8], eax
0x1400192de  mov     eax, dword ptr [rbp+57h+var_A8]
0x1400192e1  mov     rcx, cs:qword_1400CF798
0x1400192e8  lea     rax, [rbp+57h+var_80]
0x1400192ec  mov     [rsp+0E0h+var_B8], rax
0x1400192f1  mov     [rsp+0E0h+var_C0], 5
0x1400192f9  call    cs:__imp_EtwEventWriteTransfer
0x1400192ff  mov     r15, [rsp+0E0h+var_20]
0x140019307  mov     r13, [rsp+0E0h+arg_10]
0x14001930f  test    rdi, rdi
0x140019312  jz      short loc_14001931D
0x140019314  mov     rcx, rdi; SRWLock
0x140019317  call    cs:__imp_ReleaseSRWLockExclusive
0x14001931d  xor     eax, eax
0x14001931f  jmp     short loc_140019356
0x140019321  mov     rcx, [rbp+5Fh]; this
0x140019325  lea     r8, aClientcoreDsSe_3; "clientcore\\ds\\security\\umstartup\\wi"...
0x14001932c  mov     r9d, 8007000Eh; char *
0x140019332  mov     [rsi+148h], r14
0x140019339  mov     edx, 639h; void *
0x14001933e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019343  test    rdi, rdi
0x140019346  jz      short loc_140019351
0x140019348  mov     rcx, rdi; SRWLock
0x14001934b  call    cs:__imp_ReleaseSRWLockExclusive
0x140019351  mov     eax, 8007000Eh
0x140019356  mov     rbx, [rsp+0E0h+arg_8]
0x14001935e  mov     r14, [rsp+0E0h+arg_18]
0x140019366  mov     rcx, [rbp+57h+var_30]
0x14001936a  xor     rcx, rsp; StackCookie
0x14001936d  call    __security_check_cookie
0x140019372  add     rsp, 0C8h
0x140019379  pop     r12
0x14001937b  pop     rdi
0x14001937c  pop     rsi
0x14001937d  pop     rbp
0x14001937e  retn
```
