# CPerfTraceHelper::ProcessPerformanceData(ulong,long,ushort const *)

- ea: `0x180014b60`
- end: `0x180014dc8`
- name: `?ProcessPerformanceData@CPerfTraceHelper@@QEAAXKJPEBG@Z`
- size: `616`
- prototype: `void(CPerfTraceHelper *__hidden this, unsigned int, int, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002cf0`
- `0x180008710`
- `0x18000e840`
- `0x18000ef50`
- `0x18000ff40`
- `0x180012cc0`
- `0x180015a90`
- `0x180016780`
- `0x18001cea0`
- `0x18003ab88`
- `0x1800437e0`
- `0x180047160`
- `0x18006fcd0`

## callees

- `0x180014b60`
- `0x180041ab0`
- `0x18006d490`
- `0x18006ef64`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180014bb9`
- `KERNEL32!QueryPerformanceCounter` at `0x180014d5e`
- `KERNEL32!QueryPerformanceCounter` at `0x180014bb9`
- `KERNEL32!QueryPerformanceCounter` at `0x180014d5e`
- `KERNEL32!QueryPerformanceFrequency` at `0x180014bcc`
- `KERNEL32!QueryPerformanceFrequency` at `0x180014bcc`
- `KERNEL32!GetCurrentThreadId` at `0x180014cdb`
- `KERNEL32!GetCurrentThreadId` at `0x180014cdb`

## pseudocode

```c
void __fastcall CPerfTraceHelper::ProcessPerformanceData(
        LARGE_INTEGER *this,
        int a2,
        char a3,
        const unsigned __int16 *a4)
{
  PVOID *v7; // r9
  LONG HighPart; // ebx
  LARGE_INTEGER v9; // rdi
  CPerfTraceHelper *v10; // rcx
  const unsigned __int16 *CommandName; // rax
  char v12; // r8
  char v13; // r10
  char v14; // r11
  int v15; // [rsp+48h] [rbp-60h]
  int v16; // [rsp+58h] [rbp-50h]
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+8h] BYREF

  PerformanceCount.QuadPart = 0;
  if ( a2 == this->LowPart && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(&PerformanceCount);
    if ( this[6].QuadPart || QueryPerformanceFrequency(this + 6) && this[6].QuadPart )
    {
      switch ( this->LowPart )
      {
        case 1u:
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
            goto LABEL_13;
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
          goto LABEL_11;
        case 2u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
        case 0xBu:
LABEL_11:
          v7 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_13;
        default:
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
LABEL_13:
            if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x800) != 0 )
            {
              HighPart = this->HighPart;
              v9 = this[1];
              GetCurrentThreadId();
              if ( !a4 )
                a4 = L"N/A";
              CommandName = CPerfTraceHelper::GetCommandName(v10, this->LowPart);
              WPP_SF_dDSdiddddDS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                (__int64)CommandName,
                v13,
                v9.QuadPart,
                v12,
                v15,
                HighPart,
                v16,
                a3,
                (__int64)a4);
            }
            QueryPerformanceCounter(this + 3);
            LOBYTE(this[7].LowPart) = 0;
          }
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x180014b60  push    rbp
0x180014b62  push    rsi
0x180014b63  push    r14
0x180014b65  sub     rsp, 90h
0x180014b6c  mov     rbp, r9
0x180014b6f  mov     r14d, r8d
0x180014b72  mov     rsi, rcx
0x180014b75  mov     qword ptr [rsp+0A8h+PerformanceCount], 0
0x180014b81  cmp     edx, [rcx]
0x180014b83  jz      short loc_180014B91
0x180014b85  add     rsp, 90h
0x180014b8c  pop     r14
0x180014b8e  pop     rsi
0x180014b8f  pop     rbp
0x180014b90  retn
0x180014b91  mov     rax, cs:WPP_GLOBAL_Control
0x180014b98  test    dword ptr [rax+1Ch], 800h
0x180014b9f  jz      short loc_180014B85
0x180014ba1  mov     [rsp+0A8h+arg_8], rbx
0x180014ba9  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x180014bb1  mov     [rsp+0A8h+var_28], r15
0x180014bb9  call    cs:__imp_QueryPerformanceCounter
0x180014bbf  mov     r15, [rsi+30h]
0x180014bc3  test    r15, r15
0x180014bc6  jnz     short loc_180014BE7
0x180014bc8  lea     rcx, [rsi+30h]; lpFrequency
0x180014bcc  call    cs:__imp_QueryPerformanceFrequency
0x180014bd2  test    eax, eax
0x180014bd4  jz      loc_180014D85
0x180014bda  mov     r15, [rsi+30h]
0x180014bde  test    r15, r15
0x180014be1  jz      loc_180014D85
0x180014be7  mov     eax, [rsi]
0x180014be9  mov     rcx, r15
0x180014bec  mov     [rsp+0A8h+arg_10], rdi
0x180014bf4  lea     rdi, WPP_GLOBAL_Control
0x180014bfb  mov     [rsp+0A8h+var_20], r13
0x180014c03  mov     r13, qword ptr [rsp+0A8h+PerformanceCount]
0x180014c0b  sub     r13, [rsi+10h]
0x180014c0f  dec     eax; switch 11 cases
0x180014c11  cmp     eax, 0Ah
0x180014c14  ja      short def_180014C27; jumptable 0000000180014C27 default case, case 3
0x180014c16  lea     rdx, __ImageBase
0x180014c1d  mov     eax, ds:(jpt_180014C27 - 180000000h)[rdx+rax*4]
0x180014c24  add     rax, rdx
0x180014c27  jmp     rax; switch jump
0x180014c29  mov     r9, cs:WPP_GLOBAL_Control; jumptable 0000000180014C27 case 1
0x180014c30  cmp     r9, rdi
0x180014c33  jz      short loc_180014C79
0x180014c35  test    dword ptr [r9+1Ch], 800h
0x180014c3d  jz      short loc_180014C79
0x180014c3f  mov     rcx, [r9+10h]
0x180014c43  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x180014c4a  mov     edx, 7Dh ; '}'
0x180014c4f  call    WPP_SF_
0x180014c54  mov     r15, [rsi+30h]
0x180014c58  mov     rcx, r15
0x180014c5b  mov     r9, cs:WPP_GLOBAL_Control; jumptable 0000000180014C27 cases 2,4-11
0x180014c62  jmp     short loc_180014C79
0x180014c64  mov     r9, cs:WPP_GLOBAL_Control; jumptable 0000000180014C27 default case, case 3
0x180014c6b  test    dword ptr [r9+1Ch], 1000h
0x180014c73  jz      loc_180014D75
0x180014c79  mov     rdx, [rsi+18h]
0x180014c7d  mov     [rsp+0A8h+arg_18], r12
0x180014c85  movaps  [rsp+0A8h+var_38], xmm6
0x180014c8a  test    rdx, rdx
0x180014c8d  jnz     short loc_180014C94
0x180014c8f  xorps   xmm6, xmm6
0x180014c92  jmp     short loc_180014CBD
0x180014c94  mov     rax, [rsi+10h]
0x180014c98  xorps   xmm1, xmm1
0x180014c9b  sub     rax, rdx
0x180014c9e  xorps   xmm0, xmm0
0x180014ca1  cvtsi2sd xmm0, rcx
0x180014ca6  mov     r15, rcx
0x180014ca9  cvtsi2sd xmm1, rax
0x180014cae  divsd   xmm1, xmm0
0x180014cb2  mulsd   xmm1, cs:__real@408f400000000000
0x180014cba  movaps  xmm6, xmm1
0x180014cbd  cmp     r9, rdi
0x180014cc0  jz      loc_180014D5A
0x180014cc6  test    dword ptr [r9+1Ch], 800h
0x180014cce  jz      loc_180014D5A
0x180014cd4  mov     ebx, [rsi+4]
0x180014cd7  mov     rdi, [rsi+8]
0x180014cdb  call    cs:__imp_GetCurrentThreadId
0x180014ce1  mov     r11d, [rsi]
0x180014ce4  xorps   xmm1, xmm1
0x180014ce7  cvtsi2sd xmm1, r13
0x180014cec  mov     r10d, eax
0x180014cef  lea     rax, aNA; "N/A"
0x180014cf6  test    rbp, rbp
0x180014cf9  mov     edx, r11d; unsigned int
0x180014cfc  cmovz   rbp, rax
0x180014d00  xorps   xmm0, xmm0
0x180014d03  cvtsi2sd xmm0, r15
0x180014d08  divsd   xmm1, xmm0
0x180014d0c  mulsd   xmm1, cs:__real@408f400000000000
0x180014d14  cvttsd2si r8, xmm1
0x180014d19  call    ?GetCommandName@CPerfTraceHelper@@QEAAPEBGK@Z; CPerfTraceHelper::GetCommandName(ulong)
0x180014d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d25  mov     [rsp+0A8h+var_40], rbp; __int64
0x180014d2a  mov     dword ptr [rsp+0A8h+var_48], r14d; char
0x180014d2f  mov     dword ptr [rsp+0A8h+var_58], ebx; char
0x180014d33  mov     rcx, [rcx+10h]; LoggerHandle
0x180014d37  mov     dword ptr [rsp+0A8h+var_68], r8d; char
0x180014d3c  mov     qword ptr [rsp+0A8h+var_70], rdi; char
0x180014d41  mov     dword ptr [rsp+0A8h+var_78], r10d; char
0x180014d46  mov     [rsp+0A8h+var_80], rax; __int64
0x180014d4b  cvttsd2si r9, xmm6
0x180014d50  mov     dword ptr [rsp+0A8h+var_88], r11d; char
0x180014d55  call    WPP_SF_dDSdiddddDS
0x180014d5a  lea     rcx, [rsi+18h]; lpPerformanceCount
0x180014d5e  call    cs:__imp_QueryPerformanceCounter
0x180014d64  movaps  xmm6, [rsp+0A8h+var_38]
0x180014d69  mov     r12, [rsp+0A8h+arg_18]
0x180014d71  mov     byte ptr [rsi+38h], 0
0x180014d75  mov     r13, [rsp+0A8h+var_20]
0x180014d7d  mov     rdi, [rsp+0A8h+arg_10]
0x180014d85  mov     rbx, [rsp+0A8h+arg_8]
0x180014d8d  mov     r15, [rsp+0A8h+var_28]
0x180014d95  jmp     loc_180014B85
```
