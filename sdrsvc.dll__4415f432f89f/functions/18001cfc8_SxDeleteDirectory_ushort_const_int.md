# SxDeleteDirectory(ushort const *,int)

- ea: `0x18001cfc8`
- end: `0x18001d14e`
- name: `?SxDeleteDirectory@@YAJPEBGH@Z`
- size: `390`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800148dc`

## callees

- `0x18000ea0c`
- `0x180014f70`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001cfc8`
- `0x18001d4dc`
- `0x18001dd98`
- `0x18001f624`
- `0x18001fd94`
- `0x180020488`

## string_xrefs

- `0x18001d014`: `SxDeleteDirectory`

## pseudocode

```c
__int64 __fastcall SxDeleteDirectory(const unsigned __int16 *a1)
{
  __int16 v2; // ax
  int LastFailureAsHRESULT; // ebx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-50h] BYREF
  int v8; // [rsp+30h] [rbp-40h] BYREF
  __int16 v9; // [rsp+34h] [rbp-3Ch]
  __int16 v10; // [rsp+36h] [rbp-3Ah]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxDeleteDirectory", 0x7D2u, 1u);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_180028260;
  v2 = 2007;
  if ( a1 )
  {
    v8 = 0;
    v9 = 2007;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, a1);
    }
    LastFailureAsHRESULT = CBsString::Append((CBsString *)lpFileName, a1);
    v8 = LastFailureAsHRESULT;
    v2 = 2011;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_6;
    v9 = 2011;
    CBsString::TrimRight((CBsString *)lpFileName, v4);
    v5 = DeleteDirectory(lpFileName[0]);
    if ( v5 < 0 )
    {
      if ( v5 != -2147024751 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v8 = LastFailureAsHRESULT;
        v2 = 2029;
        goto LABEL_6;
      }
      v8 = 0;
      v9 = 2029;
      LastFailureAsHRESULT = SxTraverseFilesFirst((unsigned __int16 *)lpFileName[0]);
      v8 = LastFailureAsHRESULT;
      v2 = 2031;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_6;
    }
    else
    {
      v8 = 0;
      v2 = 2020;
      LastFailureAsHRESULT = 0;
    }
    v9 = v2;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = -2147024809;
  v8 = -2147024809;
LABEL_6:
  v10 = v2;
LABEL_17:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001cfc8  mov     [rsp-8+arg_0], rbx
0x18001cfcd  mov     [rsp-8+arg_8], rsi
0x18001cfd2  push    rbp
0x18001cfd3  mov     rbp, rsp
0x18001cfd6  sub     rsp, 70h
0x18001cfda  mov     rbx, rcx
0x18001cfdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfe4  lea     rsi, WPP_GLOBAL_Control
0x18001cfeb  cmp     rcx, rsi
0x18001cfee  jz      short loc_18001D00E
0x18001cff0  test    dword ptr [rcx+1Ch], 20000000h
0x18001cff7  jz      short loc_18001D00E
0x18001cff9  mov     rcx, [rcx+10h]
0x18001cffd  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d004  mov     edx, 37h ; '7'
0x18001d009  call    WPP_SF_
0x18001d00e  mov     r9d, 1; unsigned __int16
0x18001d014  lea     rdx, aSxdeletedirect; "SxDeleteDirectory"
0x18001d01b  mov     r8d, 7D2h; unsigned __int16
0x18001d021  lea     rcx, [rbp+var_40]; this
0x18001d025  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d02a  mov     [rbp+var_48], 0
0x18001d032  lea     rax, qword_180028260
0x18001d039  mov     [rbp+lpFileName], rax
0x18001d03d  mov     eax, 7D7h
0x18001d042  test    rbx, rbx
0x18001d045  jnz     short loc_18001D058
0x18001d047  mov     ebx, 80070057h
0x18001d04c  mov     [rbp+var_40], ebx
0x18001d04f  mov     [rbp+var_3A], ax
0x18001d053  jmp     loc_18001D128
0x18001d058  mov     [rbp+var_40], 0
0x18001d05f  mov     [rbp+var_3C], ax
0x18001d063  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d06a  cmp     rcx, rsi
0x18001d06d  jz      short loc_18001D090
0x18001d06f  test    dword ptr [rcx+1Ch], 10000000h
0x18001d076  jz      short loc_18001D090
0x18001d078  mov     rcx, [rcx+10h]
0x18001d07c  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d083  mov     edx, 38h ; '8'
0x18001d088  mov     r9, rbx
0x18001d08b  call    WPP_SF_S
0x18001d090  mov     rdx, rbx; unsigned __int16 *
0x18001d093  lea     rcx, [rbp+lpFileName]; this
0x18001d097  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001d09c  mov     ebx, eax
0x18001d09e  mov     [rbp+var_40], eax
0x18001d0a1  test    eax, eax
0x18001d0a3  mov     eax, 7DBh
0x18001d0a8  js      short loc_18001D04F
0x18001d0aa  lea     rcx, [rbp+lpFileName]; this
0x18001d0ae  mov     [rbp+var_3C], ax
0x18001d0b2  call    ?TrimRight@CBsString@@QEAAXPEBG@Z; CBsString::TrimRight(ushort const *)
0x18001d0b7  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001d0bb  call    _DeleteDirectory
0x18001d0c0  test    eax, eax
0x18001d0c2  js      short loc_18001D0D4
0x18001d0c4  mov     [rbp+var_40], 0
0x18001d0cb  mov     eax, 7E4h
0x18001d0d0  xor     ebx, ebx
0x18001d0d2  jmp     short loc_18001D124
0x18001d0d4  cmp     eax, 80070091h
0x18001d0d9  jz      short loc_18001D0EF
0x18001d0db  call    GetLastFailureAsHRESULT
0x18001d0e0  mov     ebx, eax
0x18001d0e2  mov     [rbp+var_40], eax
0x18001d0e5  mov     eax, 7EDh
0x18001d0ea  jmp     loc_18001D04F
0x18001d0ef  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x18001d0f3  lea     rdx, _DeleteDirectoryTraverseCallback
0x18001d0fa  mov     eax, 7EDh
0x18001d0ff  mov     [rbp+var_40], 0
0x18001d106  xor     r8d, r8d
0x18001d109  mov     [rbp+var_3C], ax
0x18001d10d  call    ?SxTraverseFilesFirst@@YAJPEBGP6AJPEAX0H@_E1@Z; SxTraverseFilesFirst(ushort const *,long (*)(void *,ushort const *,int),...)
0x18001d112  mov     ebx, eax
0x18001d114  mov     [rbp+var_40], eax
0x18001d117  test    eax, eax
0x18001d119  mov     eax, 7EFh
0x18001d11e  js      loc_18001D04F
0x18001d124  mov     [rbp+var_3C], ax
0x18001d128  lea     rcx, [rbp+lpFileName]; this
0x18001d12c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001d131  lea     rcx, [rbp+var_40]; this
0x18001d135  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d13a  lea     r11, [rsp+70h+var_s0]
0x18001d13f  mov     eax, ebx
0x18001d141  mov     rbx, [r11+10h]
0x18001d145  mov     rsi, [r11+18h]
0x18001d149  mov     rsp, r11
0x18001d14c  pop     rbp
0x18001d14d  retn
```
