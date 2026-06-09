# SxDeleteFile(ushort const *)

- ea: `0x18000dd64`
- end: `0x18000dea6`
- name: `?SxDeleteFile@@YAJPEBG@Z`
- size: `322`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180002054`
- `0x1800022e4`
- `0x180002658`
- `0x180002818`
- `0x180004e20`
- `0x18000572c`
- `0x180005c6c`

## callees

- `0x180003ce0`
- `0x18000ceb4`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dc78`
- `0x18000dd64`
- `0x18000deac`
- `0x18000f154`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000de11`
- `KERNEL32!GetLastError` at `0x18000de11`
- `KERNEL32!DeleteFileW` at `0x18000ddf7`
- `KERNEL32!DeleteFileW` at `0x18000de4d`
- `KERNEL32!DeleteFileW` at `0x18000ddf7`
- `KERNEL32!DeleteFileW` at `0x18000de4d`

## string_xrefs

- `0x18000ddb0`: `SxDeleteFile`

## pseudocode

```c
__int64 __fastcall SxDeleteFile(LPCWSTR lpFileName)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v6; // ax
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  unsigned int v11; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxDeleteFile", 1311);
  v11 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( DeleteFileW(lpFileName) )
  {
    v4 = 1319;
LABEL_9:
    LastFailureAsHRESULT = 0;
    v9 = v4;
    v8 = 0;
    goto LABEL_19;
  }
  if ( GetLastError() == 2 )
  {
    v4 = 1323;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v11);
  v8 = LastFailureAsHRESULT;
  v6 = 1329;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_13;
  v9 = 1329;
  if ( !DeleteFileW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v8 = LastFailureAsHRESULT;
    v6 = 1334;
LABEL_13:
    v2 = v11;
    v10 = v6;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = 0;
  v8 = 0;
  v2 = 0xFFFFFFFFLL;
  v9 = 1334;
LABEL_17:
  if ( (_DWORD)v2 != -1 )
  {
    SxSetFileAttributes(lpFileName, v2);
    LastFailureAsHRESULT = v8;
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8, v2, v3);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000dd64  mov     [rsp-8+arg_0], rbx
0x18000dd69  mov     [rsp-8+arg_10], rdi
0x18000dd6e  push    rbp
0x18000dd6f  mov     rbp, rsp
0x18000dd72  sub     rsp, 60h
0x18000dd76  mov     rdi, rcx
0x18000dd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd80  lea     rbx, WPP_GLOBAL_Control
0x18000dd87  cmp     rcx, rbx
0x18000dd8a  jz      short loc_18000DDAA
0x18000dd8c  test    dword ptr [rcx+1Ch], 20000000h
0x18000dd93  jz      short loc_18000DDAA
0x18000dd95  mov     rcx, [rcx+10h]
0x18000dd99  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18000dda0  mov     edx, 29h ; ')'
0x18000dda5  call    WPP_SF_
0x18000ddaa  mov     r8d, 51Fh; unsigned __int16
0x18000ddb0  lea     rdx, aSxdeletefile; "SxDeleteFile"
0x18000ddb7  lea     rcx, [rbp+var_40]; this
0x18000ddbb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ddc0  mov     [rbp+arg_8], 0FFFFFFFFh
0x18000ddc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddce  cmp     rcx, rbx
0x18000ddd1  jz      short loc_18000DDF4
0x18000ddd3  test    dword ptr [rcx+1Ch], 10000000h
0x18000ddda  jz      short loc_18000DDF4
0x18000dddc  mov     rcx, [rcx+10h]
0x18000dde0  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18000dde7  mov     edx, 2Ah ; '*'
0x18000ddec  mov     r9, rdi
0x18000ddef  call    WPP_SF_S
0x18000ddf4  mov     rcx, rdi; lpFileName
0x18000ddf7  call    cs:__imp_DeleteFileW
0x18000ddfd  test    eax, eax
0x18000ddff  jz      short loc_18000DE11
0x18000de01  mov     eax, 527h
0x18000de06  xor     ebx, ebx
0x18000de08  mov     [rbp+var_3C], ax
0x18000de0c  mov     [rbp+var_40], ebx
0x18000de0f  jmp     short loc_18000DE89
0x18000de11  call    cs:__imp_GetLastError
0x18000de17  cmp     eax, 2
0x18000de1a  jnz     short loc_18000DE23
0x18000de1c  mov     eax, 52Bh
0x18000de21  jmp     short loc_18000DE06
0x18000de23  lea     rdx, [rbp+arg_8]; unsigned int *
0x18000de27  mov     rcx, rdi; lpFileName
0x18000de2a  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x18000de2f  mov     ebx, eax
0x18000de31  mov     [rbp+var_40], eax
0x18000de34  test    eax, eax
0x18000de36  mov     eax, 531h
0x18000de3b  jns     short loc_18000DE46
0x18000de3d  mov     edx, [rbp+arg_8]
0x18000de40  mov     [rbp+var_3A], ax
0x18000de44  jmp     short loc_18000DE79
0x18000de46  mov     rcx, rdi; lpFileName
0x18000de49  mov     [rbp+var_3C], ax
0x18000de4d  call    cs:__imp_DeleteFileW
0x18000de53  test    eax, eax
0x18000de55  jnz     short loc_18000DE68
0x18000de57  call    GetLastFailureAsHRESULT
0x18000de5c  mov     ebx, eax
0x18000de5e  mov     [rbp+var_40], eax
0x18000de61  mov     eax, 536h
0x18000de66  jmp     short loc_18000DE3D
0x18000de68  xor     ebx, ebx
0x18000de6a  mov     eax, 536h
0x18000de6f  mov     [rbp+var_40], ebx
0x18000de72  or      edx, 0FFFFFFFFh; unsigned int
0x18000de75  mov     [rbp+var_3C], ax
0x18000de79  cmp     edx, 0FFFFFFFFh
0x18000de7c  jz      short loc_18000DE89
0x18000de7e  mov     rcx, rdi; lpFileName
0x18000de81  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x18000de86  mov     ebx, [rbp+var_40]
0x18000de89  lea     rcx, [rbp+var_40]; this
0x18000de8d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000de92  lea     r11, [rsp+60h+var_s0]
0x18000de97  mov     eax, ebx
0x18000de99  mov     rbx, [r11+10h]
0x18000de9d  mov     rdi, [r11+20h]
0x18000dea1  mov     rsp, r11
0x18000dea4  pop     rbp
0x18000dea5  retn
```
