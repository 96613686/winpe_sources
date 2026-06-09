# CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(ulong,WinLogonActivityStopReason,WinLogonActivityType,int,int,int,ulong,int)

- ea: `0x140044830`
- end: `0x140044bb5`
- name: `?StopAndDeleteGlobalTraceLoggingActivity@CGlobalStore@@QEAAJKW4WinLogonActivityStopReason@@W4WinLogonActivityType@@HHHKH@Z`
- size: `901`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400176f8`
- `0x140044c90`
- `0x14004d7ec`
- `0x1400500f0`
- `0x140051d40`
- `0x14006e220`
- `0x14006e950`
- `0x140070920`
- `0x140084470`

## callees

- `0x14000aa04`
- `0x140044830`
- `0x1400533e4`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004489e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140044b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004489e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140044b8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140044869`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140044869`
- `ntdll!EtwEventWriteTransfer` at `0x140044a6f`
- `ntdll!EtwEventWriteTransfer` at `0x140044b4e`
- `ntdll!EtwEventWriteTransfer` at `0x140044a6f`
- `ntdll!EtwEventWriteTransfer` at `0x140044b4e`

## string_xrefs

- `0x14004487f`: `clientcore\ds\security\umstartup\winlogon\core\globalstore.cxx`

## pseudocode

```c
__int64 __fastcall CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        char a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9)
{
  RTL_SRWLOCK *v9; // rdi
  _DWORD *Ptr; // r8
  _DWORD *v16; // rbx
  int v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  char *v26; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  char *v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  char *v32; // [rsp+90h] [rbp-70h] BYREF
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  char *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  __int64 *v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  char *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  char *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  __int64 *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  char *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  unsigned __int64 *v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  char *v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]
  unsigned __int64 *v54; // [rsp+130h] [rbp+30h]
  __int64 v55; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v9 = a1 + 8;
  AcquireSRWLockExclusive(a1 + 8);
  Ptr = a1[41].Ptr;
  if ( Ptr )
  {
    *Ptr = 2;
    if ( (unsigned int)dword_1400CF778 > 5
      && (qword_1400CF788 & 0x400000000000LL) != 0
      && (qword_1400CF790 & 0x400000000000LL) == qword_1400CF790 )
    {
      v19 = __PAIR64__(a8, a9);
      v20 = __PAIR64__(a6, a7);
      v21 = __PAIR64__(a2, a5);
      v54 = &v19;
      v52 = (char *)&v19 + 4;
      v50 = &v20;
      v48 = (char *)&v20 + 4;
      v46 = &v21;
      v44 = &v18;
      v42 = (char *)&v18 + 1;
      v40 = (char *)&v21 + 4;
      v38 = &v25;
      v23 = 517;
      v32 = (char *)off_1400CF780;
      LOBYTE(v18) = a4;
      BYTE1(v18) = a3;
      v25 = 0x1000000;
      v55 = 4;
      v53 = 4;
      v51 = 4;
      v49 = 4;
      v47 = 4;
      v45 = 1;
      v43 = 1;
      v41 = 4;
      v39 = 8;
      v22 = 184549376;
      v24 = 0x400000000000LL;
      v33 = *(unsigned __int16 *)off_1400CF780;
      v35 = byte_1400BADD9;
      v34 = 2;
      v36 = 157;
      v37 = 1;
      HIDWORD(v18) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(
        qword_1400CF798,
        &v22,
        Ptr + 2,
        0,
        11,
        &v32,
        v18,
        __PAIR64__(a8, a9),
        __PAIR64__(a6, a7),
        __PAIR64__(a2, a5));
    }
    v16 = a1[41].Ptr;
    if ( v16 )
    {
      if ( *v16 == 1 )
      {
        *v16 = 2;
        if ( (unsigned int)dword_1400CF778 > 5
          && (qword_1400CF788 & 0x400000000000LL) != 0
          && (qword_1400CF790 & 0x400000000000LL) == qword_1400CF790 )
        {
          v23 = 517;
          v26 = (char *)off_1400CF780;
          v22 = 184549376;
          v24 = 0x400000000000LL;
          v27 = *(unsigned __int16 *)off_1400CF780;
          v29 = byte_1400BADAD;
          v28 = 2;
          v30 = 32;
          v31 = 1;
          HIDWORD(v18) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1400CF798, &v22, v16 + 2, 0, 2, &v26, v18, v19, v20, v21);
        }
      }
      *v16 = 3;
      operator delete(v16, 0x28u);
    }
    a1[41].Ptr = 0;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x652,
      (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\globalstore.cxx",
      (const char *)0x8000FFFFLL,
      v17);
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x140044830  mov     [rsp-8+arg_18], rbx
0x140044835  push    rbp
0x140044836  push    rsi
0x140044837  push    rdi
0x140044838  push    r12
0x14004483a  push    r15
0x14004483c  lea     rbp, [rsp-50h]
0x140044841  sub     rsp, 150h
0x140044848  mov     rax, cs:__security_cookie
0x14004484f  xor     rax, rsp
0x140044852  mov     [rbp+70h+var_30], rax
0x140044856  lea     rdi, [rcx+40h]
0x14004485a  mov     rsi, rcx
0x14004485d  mov     rcx, rdi; SRWLock
0x140044860  mov     ebx, r9d
0x140044863  mov     r15d, r8d
0x140044866  mov     r12d, edx
0x140044869  call    cs:__imp_AcquireSRWLockExclusive
0x14004486f  mov     r8, [rsi+148h]
0x140044876  test    r8, r8
0x140044879  jnz     short loc_1400448AE
0x14004487b  mov     rcx, [rbp+78h]; this
0x14004487f  lea     r8, aClientcoreDsSe_3; "clientcore\\ds\\security\\umstartup\\wi"...
0x140044886  mov     r9d, 8000FFFFh; char *
0x14004488c  mov     edx, 652h; void *
0x140044891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044896  test    rdi, rdi
0x140044899  jz      short loc_1400448A4
0x14004489b  mov     rcx, rdi; SRWLock
0x14004489e  call    cs:__imp_ReleaseSRWLockExclusive
0x1400448a4  mov     eax, 8000FFFFh
0x1400448a9  jmp     loc_140044B92
0x1400448ae  mov     [rsp+170h+arg_8], r13
0x1400448b6  lea     r9, _TraceLoggingMetadata
0x1400448bd  mov     dword ptr [r8], 2
0x1400448c4  mov     r13, 400000000000h
0x1400448ce  mov     eax, cs:dword_1400CF778
0x1400448d4  mov     [rsp+170h+arg_10], r14
0x1400448dc  lea     r14, _TraceLoggingMetadataEnd
0x1400448e3  cmp     eax, 5
0x1400448e6  jbe     loc_140044A7C
0x1400448ec  mov     rcx, cs:qword_1400CF790
0x1400448f3  mov     rax, cs:qword_1400CF788
0x1400448fa  test    r13, rax
0x1400448fd  jz      loc_140044A7C
0x140044903  mov     rax, rcx
0x140044906  and     rax, r13
0x140044909  cmp     rax, rcx
0x14004490c  jnz     loc_140044A7C
0x140044912  mov     eax, [rbp+70h+arg_40]
0x140044918  lea     rdx, [rsp+170h+var_120]
0x14004491d  mov     dword ptr [rsp+170h+var_138], eax
0x140044921  add     r8, 8
0x140044925  mov     eax, [rbp+70h+arg_38]
0x14004492b  mov     dword ptr [rsp+170h+var_138+4], eax
0x14004492f  mov     eax, [rbp+70h+arg_30]
0x140044935  mov     dword ptr [rsp+170h+var_130], eax
0x140044939  mov     eax, [rbp+70h+arg_28]
0x14004493f  mov     dword ptr [rsp+170h+var_130+4], eax
0x140044943  mov     eax, [rbp+70h+arg_20]
0x140044949  mov     dword ptr [rsp+170h+var_128], eax
0x14004494d  lea     rax, [rsp+170h+var_138]
0x140044952  mov     [rbp+70h+var_40], rax
0x140044956  lea     rax, [rsp+170h+var_138+4]
0x14004495b  mov     [rbp+70h+var_50], rax
0x14004495f  lea     rax, [rsp+170h+var_130]
0x140044964  mov     [rbp+70h+var_60], rax
0x140044968  lea     rax, [rsp+170h+var_130+4]
0x14004496d  mov     [rbp+70h+var_70], rax
0x140044971  lea     rax, [rsp+170h+var_128]
0x140044976  mov     [rbp+70h+var_80], rax
0x14004497a  lea     rax, [rsp+170h+var_140]
0x14004497f  mov     [rbp+70h+var_90], rax
0x140044983  lea     rax, [rsp+170h+var_13F]
0x140044988  mov     [rbp+70h+var_A0], rax
0x14004498c  lea     rax, [rsp+170h+var_128+4]
0x140044991  mov     [rbp+70h+var_B0], rax
0x140044995  lea     rax, [rsp+170h+var_110]
0x14004499a  mov     [rbp+70h+var_C0], rax
0x14004499e  movzx   eax, cs:word_1400BADCF
0x1400449a5  mov     [rsp+170h+var_11C], eax
0x1400449a9  mov     rax, cs:off_1400CF780
0x1400449b0  mov     [rbp+70h+var_E0], rax
0x1400449b4  mov     [rsp+170h+var_140], bl
0x1400449b8  mov     [rsp+170h+var_13F], r15b
0x1400449bd  mov     dword ptr [rsp+170h+var_128+4], r12d
0x1400449c2  mov     [rsp+170h+var_110], 1000000h
0x1400449cb  mov     [rbp+70h+var_38], 4
0x1400449d3  mov     [rbp+70h+var_48], 4
0x1400449db  mov     [rbp+70h+var_58], 4
0x1400449e3  mov     [rbp+70h+var_68], 4
0x1400449eb  mov     [rbp+70h+var_78], 4
0x1400449f3  mov     [rbp+70h+var_88], 1
0x1400449fb  mov     [rbp+70h+var_98], 1
0x140044a03  mov     [rbp+70h+var_A8], 4
0x140044a0b  mov     [rbp+70h+var_B8], 8
0x140044a13  mov     [rsp+170h+var_120], 0B000000h
0x140044a1b  mov     [rsp+170h+var_118], r13
0x140044a20  movzx   eax, word ptr [rax]
0x140044a23  mov     [rbp+70h+var_D8], eax
0x140044a26  lea     rax, byte_1400BADD9
0x140044a2d  mov     [rbp+70h+var_D0], rax
0x140044a31  mov     rax, r14
0x140044a34  sub     eax, r9d
0x140044a37  mov     [rbp+70h+var_D4], 2
0x140044a3e  mov     [rbp+70h+var_C8], 9Dh
0x140044a45  xor     r9d, r9d
0x140044a48  mov     [rbp+70h+var_C4], 1
0x140044a4f  mov     [rsp+170h+var_13C], eax
0x140044a53  mov     eax, [rsp+170h+var_13C]
0x140044a57  mov     rcx, cs:qword_1400CF798
0x140044a5e  lea     rax, [rbp+70h+var_E0]
0x140044a62  mov     [rsp+170h+var_148], rax
0x140044a67  mov     [rsp+170h+var_150], 0Bh
0x140044a6f  call    cs:__imp_EtwEventWriteTransfer
0x140044a75  lea     r9, _TraceLoggingMetadata
0x140044a7c  mov     rbx, [rsi+148h]
0x140044a83  test    rbx, rbx
0x140044a86  jz      loc_140044B67
0x140044a8c  cmp     dword ptr [rbx], 1
0x140044a8f  jnz     loc_140044B54
0x140044a95  mov     dword ptr [rbx], 2
0x140044a9b  mov     eax, cs:dword_1400CF778
0x140044aa1  cmp     eax, 5
0x140044aa4  jbe     loc_140044B54
0x140044aaa  mov     rcx, cs:qword_1400CF790
0x140044ab1  mov     rax, cs:qword_1400CF788
0x140044ab8  test    r13, rax
0x140044abb  jz      loc_140044B54
0x140044ac1  mov     rax, rcx
0x140044ac4  and     rax, r13
0x140044ac7  cmp     rax, rcx
0x140044aca  jnz     loc_140044B54
0x140044ad0  movzx   eax, cs:word_1400BADA3
0x140044ad7  lea     r8, [rbx+8]
0x140044adb  mov     [rsp+170h+var_11C], eax
0x140044adf  lea     rdx, [rsp+170h+var_120]
0x140044ae4  mov     rax, cs:off_1400CF780
0x140044aeb  sub     r14d, r9d
0x140044aee  mov     [rsp+170h+var_108], rax
0x140044af3  xor     r9d, r9d
0x140044af6  mov     [rsp+170h+var_120], 0B000000h
0x140044afe  mov     [rsp+170h+var_118], r13
0x140044b03  movzx   eax, word ptr [rax]
0x140044b06  mov     [rsp+170h+var_100], eax
0x140044b0a  lea     rax, byte_1400BADAD
0x140044b11  mov     [rsp+170h+var_F8], rax
0x140044b16  mov     [rsp+170h+var_FC], 2
0x140044b1e  mov     [rbp+70h+var_F0], 20h ; ' '
0x140044b25  mov     [rbp+70h+var_EC], 1
0x140044b2c  mov     [rsp+170h+var_13C], r14d
0x140044b31  mov     eax, [rsp+170h+var_13C]
0x140044b35  mov     rcx, cs:qword_1400CF798
0x140044b3c  lea     rax, [rsp+170h+var_108]
0x140044b41  mov     [rsp+170h+var_148], rax
0x140044b46  mov     [rsp+170h+var_150], 2
0x140044b4e  call    cs:__imp_EtwEventWriteTransfer
0x140044b54  mov     edx, 28h ; '('; unsigned __int64
0x140044b59  mov     dword ptr [rbx], 3
0x140044b5f  mov     rcx, rbx; void *
0x140044b62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140044b67  mov     r14, [rsp+170h+arg_10]
0x140044b6f  mov     r13, [rsp+170h+arg_8]
0x140044b77  mov     qword ptr [rsi+148h], 0
0x140044b82  test    rdi, rdi
0x140044b85  jz      short loc_140044B90
0x140044b87  mov     rcx, rdi; SRWLock
0x140044b8a  call    cs:__imp_ReleaseSRWLockExclusive
0x140044b90  xor     eax, eax
0x140044b92  mov     rcx, [rbp+70h+var_30]
0x140044b96  xor     rcx, rsp; StackCookie
0x140044b99  call    __security_check_cookie
0x140044b9e  mov     rbx, [rsp+170h+arg_18]
0x140044ba6  add     rsp, 150h
0x140044bad  pop     r15
0x140044baf  pop     r12
0x140044bb1  pop     rdi
0x140044bb2  pop     rsi
0x140044bb3  pop     rbp
0x140044bb4  retn
```
