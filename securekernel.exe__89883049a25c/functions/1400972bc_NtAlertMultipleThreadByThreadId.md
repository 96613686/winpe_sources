# NtAlertMultipleThreadByThreadId

- ea: `0x1400972bc`
- end: `0x140097494`
- name: `NtAlertMultipleThreadByThreadId`
- size: `472`
- prototype: `__int64 __fastcall(volatile void *Address, ULONGLONG ullMultiplicand)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x14000f0f0`
- `0x140034154`
- `0x140037e68`
- `0x1400442ac`
- `0x14008a11c`
- `0x1400972bc`
- `0x140097e2c`
- `0x140098a60`
- `0x1400f3620`
- `0x1400f9a80`
- `0x1400fc664`

## pseudocode

```c
__int64 __fastcall NtAlertMultipleThreadByThreadId(char *Address, ULONGLONG ullMultiplicand)
{
  unsigned int v2; // esi
  _BYTE *Pool; // rbx
  __int64 v5; // r13
  char v6; // r15
  NTSTATUS v7; // edi
  ULONG v8; // r9d
  __int64 i; // rdi
  unsigned __int64 ULong64FromUser; // rax
  __int64 v11; // rax
  __int64 j; // r14
  __int64 v13; // rcx
  ULONGLONG pullResult; // [rsp+28h] [rbp-250h] BYREF
  _BYTE *v16; // [rsp+30h] [rbp-248h]
  unsigned __int64 v17; // [rsp+38h] [rbp-240h]
  _BYTE v18[512]; // [rsp+40h] [rbp-238h] BYREF

  v2 = ullMultiplicand;
  memset_0(v18, 0, sizeof(v18));
  Pool = 0;
  v16 = 0;
  pullResult = 0;
  v5 = *((_QWORD *)KeGetPcr()->NtTib.StackBase + 9);
  v6 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  v7 = RtlULongLongMult(v2, 8u, &pullResult);
  if ( v7 >= 0 )
  {
    if ( v6 )
      ProbeForRead(Address, pullResult, v8);
    if ( v2 <= 0x40 )
    {
      Pool = v18;
      v16 = v18;
    }
    else
    {
      Pool = (_BYTE *)SkAllocatePool(512, pullResult);
      v16 = Pool;
      if ( !Pool )
      {
        v7 = -1073741801;
        goto LABEL_19;
      }
    }
    memset_0(Pool, 0, pullResult);
    for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
    {
      if ( v6 )
        ULong64FromUser = RtlReadULong64FromUser(&Address[8 * i]);
      else
        ULong64FromUser = *(_QWORD *)&Address[8 * i];
      v17 = ULong64FromUser;
      v11 = SkiAcquireThreadRundown((ULong64FromUser >> 2) & 0x1FFFFFFF);
      if ( !v11 )
      {
        v7 = -1073741811;
        goto LABEL_19;
      }
      *(_QWORD *)&Pool[8 * i] = v11;
      if ( v5 != *(_QWORD *)(v11 + 72) )
      {
        v7 = -1073741790;
        goto LABEL_19;
      }
    }
    SkeAlertMultipleThreadByThreadId(Pool, v2);
    v7 = 0;
  }
LABEL_19:
  if ( Pool )
  {
    for ( j = 0; (unsigned int)j < v2; j = (unsigned int)(j + 1) )
    {
      v13 = *(_QWORD *)&Pool[8 * j];
      if ( v13 )
        SkReleaseRundownProtection(v13 + 216, 0);
    }
    if ( Pool != v18 )
      SkFreePool(512, Pool);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400972bc  mov     [rsp+arg_10], rbx
0x1400972c1  mov     [rsp+arg_18], rsi
0x1400972c6  push    rdi
0x1400972c7  push    r12
0x1400972c9  push    r13
0x1400972cb  push    r14
0x1400972cd  push    r15
0x1400972cf  sub     rsp, 250h
0x1400972d6  mov     rax, cs:__security_cookie
0x1400972dd  xor     rax, rsp
0x1400972e0  mov     [rsp+278h+var_38], rax
0x1400972e8  mov     esi, edx
0x1400972ea  mov     r12, rcx
0x1400972ed  mov     [rsp+278h+var_258], esi
0x1400972f1  xor     edx, edx; Val
0x1400972f3  mov     r8d, 200h; Size
0x1400972f9  lea     rcx, [rsp+278h+var_238]; void *
0x1400972fe  call    memset_0
0x140097303  xor     ebx, ebx
0x140097305  mov     [rsp+278h+var_248], rbx
0x14009730a  mov     [rsp+278h+pullResult], rbx
0x14009730f  mov     rax, gs:8
0x140097318  mov     r13, [rax+48h]
0x14009731c  mov     rax, gs:8
0x140097325  mov     r15b, [rax+60h]
0x140097329  mov     ecx, esi; ullMultiplicand
0x14009732b  lea     r8, [rsp+278h+pullResult]; pullResult
0x140097330  lea     r9d, [rbx+8]
0x140097334  mov     edx, r9d; ullMultiplier
0x140097337  call    RtlULongLongMult
0x14009733c  mov     edi, eax
0x14009733e  test    eax, eax
0x140097340  js      loc_140097422
0x140097346  test    r15b, r15b
0x140097349  jz      short loc_14009736D
0x14009734b  mov     r8d, r9d; Alignment
0x14009734e  mov     rdx, [rsp+278h+pullResult]; Length
0x140097353  mov     rcx, r12; Address
0x140097356  call    ProbeForRead
0x14009735b  jmp     short loc_14009736D
0x14009735d  mov     edi, eax
0x14009735f  mov     rbx, [rsp+278h+var_248]
0x140097364  mov     esi, [rsp+278h+var_258]
0x140097368  jmp     loc_140097422
0x14009736d  cmp     esi, 40h ; '@'
0x140097370  jbe     short loc_14009739E
0x140097372  mov     r8d, 6D41654Bh
0x140097378  mov     rdx, [rsp+278h+pullResult]
0x14009737d  mov     ecx, 200h
0x140097382  call    SkAllocatePool
0x140097387  mov     rbx, rax
0x14009738a  mov     [rsp+278h+var_248], rax
0x14009738f  test    rax, rax
0x140097392  jnz     short loc_1400973A8
0x140097394  mov     edi, 0C0000017h
0x140097399  jmp     loc_140097422
0x14009739e  lea     rbx, [rsp+278h+var_238]
0x1400973a3  mov     [rsp+278h+var_248], rbx
0x1400973a8  mov     r8, [rsp+278h+pullResult]; Size
0x1400973ad  xor     edx, edx; Val
0x1400973af  mov     rcx, rbx; void *
0x1400973b2  call    memset_0
0x1400973b7  xor     edi, edi
0x1400973b9  cmp     edi, esi
0x1400973bb  jnb     short loc_140097416
0x1400973bd  lea     rax, [r12+rdi*8]
0x1400973c1  test    r15b, r15b
0x1400973c4  jz      short loc_1400973D0
0x1400973c6  mov     rcx, rax
0x1400973c9  call    RtlReadULong64FromUser
0x1400973ce  jmp     short loc_1400973D3
0x1400973d0  mov     rax, [rax]
0x1400973d3  mov     [rsp+278h+var_240], rax
0x1400973d8  shr     rax, 2
0x1400973dc  and     eax, 1FFFFFFFh
0x1400973e1  mov     ecx, eax
0x1400973e3  call    SkiAcquireThreadRundown
0x1400973e8  test    rax, rax
0x1400973eb  jnz     short loc_1400973F4
0x1400973ed  mov     edi, 0C000000Dh
0x1400973f2  jmp     short loc_140097422
0x1400973f4  mov     [rbx+rdi*8], rax
0x1400973f8  cmp     r13, [rax+48h]
0x1400973fc  jz      short loc_140097405
0x1400973fe  mov     edi, 0C0000022h
0x140097403  jmp     short loc_140097422
0x140097405  inc     edi
0x140097407  jmp     short loc_1400973B9
0x140097409  mov     edi, eax
0x14009740b  mov     rbx, [rsp+278h+var_248]
0x140097410  mov     esi, [rsp+278h+var_258]
0x140097414  jmp     short loc_140097422
0x140097416  mov     edx, esi
0x140097418  mov     rcx, rbx
0x14009741b  call    SkeAlertMultipleThreadByThreadId
0x140097420  xor     edi, edi
0x140097422  test    rbx, rbx
0x140097425  jz      short loc_140097464
0x140097427  xor     r14d, r14d
0x14009742a  test    esi, esi
0x14009742c  jz      short loc_14009744D
0x14009742e  mov     rcx, [rbx+r14*8]
0x140097432  test    rcx, rcx
0x140097435  jz      short loc_140097445
0x140097437  add     rcx, 0D8h
0x14009743e  xor     edx, edx
0x140097440  call    SkReleaseRundownProtection
0x140097445  inc     r14d
0x140097448  cmp     r14d, esi
0x14009744b  jb      short loc_14009742E
0x14009744d  lea     rax, [rsp+278h+var_238]
0x140097452  cmp     rbx, rax
0x140097455  jz      short loc_140097464
0x140097457  mov     rdx, rbx
0x14009745a  mov     ecx, 200h
0x14009745f  call    SkFreePool
0x140097464  mov     eax, edi
0x140097466  mov     rcx, [rsp+278h+var_38]
0x14009746e  xor     rcx, rsp; StackCookie
0x140097471  call    __security_check_cookie
0x140097476  lea     r11, [rsp+278h+var_28]
0x14009747e  mov     rbx, [r11+40h]
0x140097482  mov     rsi, [r11+48h]
0x140097486  mov     rsp, r11
0x140097489  pop     r15
0x14009748b  pop     r14
0x14009748d  pop     r13
0x14009748f  pop     r12
0x140097491  pop     rdi
0x140097492  retn
```
