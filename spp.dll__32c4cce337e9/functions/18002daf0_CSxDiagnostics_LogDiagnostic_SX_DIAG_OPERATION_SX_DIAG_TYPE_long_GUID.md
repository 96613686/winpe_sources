# CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)

- ea: `0x18002daf0`
- end: `0x18002dccb`
- name: `?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006730`
- `0x180010e68`
- `0x180013c7c`
- `0x180017304`
- `0x180017960`
- `0x18001a830`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002daf0`
- `0x18002dcd4`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002dbef`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002dbef`
- `KERNEL32!GetCurrentProcessId` at `0x18002dc03`
- `KERNEL32!GetCurrentProcessId` at `0x18002dc03`
- `KERNEL32!GetCurrentThreadId` at `0x18002dc0c`
- `KERNEL32!GetCurrentThreadId` at `0x18002dc0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc63`

## pseudocode

```c
__int64 __fastcall CSxDiagnostics::LogDiagnostic(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int128 *a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int16 v11; // ax
  int Identifier; // eax
  __int16 v13; // cx
  DWORD CurrentThreadId; // eax
  __int128 v15; // xmm0
  HKEY v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-91h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+38h] [rbp-89h] BYREF
  int v22; // [rsp+48h] [rbp-79h] BYREF
  __int16 v23; // [rsp+4Ch] [rbp-75h]
  __int16 v24; // [rsp+4Eh] [rbp-73h]
  BYTE Data[8]; // [rsp+80h] [rbp-41h] BYREF
  struct _FILETIME v26; // [rsp+88h] [rbp-39h]
  DWORD CurrentProcessId; // [rsp+90h] [rbp-31h]
  DWORD v28; // [rsp+94h] [rbp-2Dh]
  unsigned int v29; // [rsp+98h] [rbp-29h]
  unsigned int v30; // [rsp+9Ch] [rbp-25h]
  int v31; // [rsp+A0h] [rbp-21h]
  int v32; // [rsp+A4h] [rbp-1Dh]
  __int128 v33; // [rsp+A8h] [rbp-19h]
  __int64 v34; // [rsp+B8h] [rbp-9h]
  __int64 v35; // [rsp+C0h] [rbp-1h]

  v9 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "CSxDiagnostics::LogDiagnostic", 183, 1);
  memset_0(Data, 0, 0x48u);
  SystemTimeAsFileTime = 0;
  lpValueName[0] = &FileName;
  v23 = 190;
  lpValueName[1] = 0;
  if ( a3 <= 1 )
  {
    v23 = 191;
    v10 = *(_QWORD *)(a1 + 8) + 1LL;
    v22 = 0;
    if ( (v10 & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v22 = 1;
      v11 = 198;
LABEL_12:
      v23 = v11;
      goto LABEL_13;
    }
    Identifier = MakeIdentifier(a2, a3, lpValueName);
    v22 = Identifier;
    v13 = 201;
    if ( Identifier >= 0 )
    {
      v23 = 201;
      *(_QWORD *)Data = 72;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v26 = SystemTimeAsFileTime;
      CurrentProcessId = GetCurrentProcessId();
      CurrentThreadId = GetCurrentThreadId();
      v15 = *a5;
      v16 = *(HKEY *)(a1 + 8);
      v28 = CurrentThreadId;
      v29 = a2;
      v30 = a3;
      v31 = 0;
      v32 = a4;
      v33 = v15;
      v34 = 0;
      v35 = 0;
      Identifier = RegSetValueExW(v16, lpValueName[0], 0, 3u, Data, 0x48u);
      if ( Identifier > 0 )
        Identifier = (unsigned __int16)Identifier | 0x80070000;
      v22 = Identifier;
      if ( Identifier >= 0 )
      {
        v22 = 0;
        v11 = 233;
        v9 = 0;
        goto LABEL_12;
      }
      v13 = 231;
    }
    v24 = v13;
    v9 = Identifier;
    goto LABEL_13;
  }
  v9 = -2147024809;
  v24 = 191;
  v22 = -2147024809;
LABEL_13:
  CBsString::_Release((unsigned __int16 **)lpValueName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22, v17, v18);
  return v9;
}

```

## disassembly

```asm
0x18002daf0  push    rbp
0x18002daf2  push    rbx
0x18002daf3  push    rsi
0x18002daf4  push    rdi
0x18002daf5  push    r12
0x18002daf7  push    r14
0x18002daf9  push    r15
0x18002dafb  lea     rbp, [rsp-1Fh]
0x18002db00  sub     rsp, 0E0h
0x18002db07  mov     rax, cs:__security_cookie
0x18002db0e  xor     rax, rsp
0x18002db11  mov     [rbp+4Fh+var_40], rax
0x18002db15  mov     r12, [rbp+4Fh+arg_20]
0x18002db19  mov     r15d, r9d
0x18002db1c  mov     edi, r8d
0x18002db1f  mov     esi, edx
0x18002db21  mov     r14, rcx
0x18002db24  lea     rdx, aCsxdiagnostics; "CSxDiagnostics::LogDiagnostic"
0x18002db2b  mov     ebx, 1
0x18002db30  lea     rcx, [rbp+4Fh+var_C8]; this
0x18002db34  mov     r9d, ebx; unsigned __int16
0x18002db37  mov     r8d, 0B7h; unsigned __int16
0x18002db3d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002db42  xor     edx, edx; Val
0x18002db44  lea     r8d, [rbx+47h]; Size
0x18002db48  lea     rcx, [rbp+4Fh+Data]; void *
0x18002db4c  call    memset_0
0x18002db51  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002db5a  lea     rax, FileName
0x18002db61  mov     [rsp+110h+lpValueName], rax
0x18002db66  mov     eax, 0BEh
0x18002db6b  mov     [rbp+4Fh+var_C4], ax
0x18002db6f  mov     eax, 0BFh
0x18002db74  mov     [rsp+110h+var_D0], 0
0x18002db7d  cmp     edi, ebx
0x18002db7f  jbe     short loc_18002DB92
0x18002db81  mov     ebx, 80070057h
0x18002db86  mov     [rbp+4Fh+var_C2], ax
0x18002db8a  mov     [rbp+4Fh+var_C8], ebx
0x18002db8d  jmp     loc_18002DC98
0x18002db92  mov     [rbp+4Fh+var_C4], ax
0x18002db96  mov     rax, [r14+8]
0x18002db9a  add     rax, rbx
0x18002db9d  mov     [rbp+4Fh+var_C8], 0
0x18002dba4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002dbaa  jnz     short loc_18002DBB9
0x18002dbac  mov     [rbp+4Fh+var_C8], ebx
0x18002dbaf  mov     eax, 0C6h
0x18002dbb4  jmp     loc_18002DC94
0x18002dbb9  lea     r8, [rsp+110h+lpValueName]
0x18002dbbe  mov     edx, edi
0x18002dbc0  mov     ecx, esi
0x18002dbc2  call    MakeIdentifier
0x18002dbc7  mov     [rbp+4Fh+var_C8], eax
0x18002dbca  mov     ecx, 0C9h
0x18002dbcf  test    eax, eax
0x18002dbd1  jns     short loc_18002DBDE
0x18002dbd3  mov     [rbp+4Fh+var_C2], cx
0x18002dbd7  mov     ebx, eax
0x18002dbd9  jmp     loc_18002DC98
0x18002dbde  mov     [rbp+4Fh+var_C4], cx
0x18002dbe2  lea     rcx, [rsp+110h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002dbe7  mov     qword ptr [rbp+4Fh+Data], 48h ; 'H'
0x18002dbef  call    cs:__imp_GetSystemTimeAsFileTime
0x18002dbf5  mov     eax, [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x18002dbf9  mov     ecx, [rsp+110h+SystemTimeAsFileTime.dwHighDateTime]
0x18002dbfd  mov     [rbp+4Fh+var_88], eax
0x18002dc00  mov     [rbp+4Fh+var_84], ecx
0x18002dc03  call    cs:__imp_GetCurrentProcessId
0x18002dc09  mov     [rbp+4Fh+var_80], eax
0x18002dc0c  call    cs:__imp_GetCurrentThreadId
0x18002dc12  movaps  xmm0, xmmword ptr [r12]
0x18002dc17  mov     r9d, 3; dwType
0x18002dc1d  mov     rdx, [rsp+110h+lpValueName]; lpValueName
0x18002dc22  xor     r8d, r8d; Reserved
0x18002dc25  mov     rcx, [r14+8]; hKey
0x18002dc29  mov     [rbp+4Fh+var_7C], eax
0x18002dc2c  lea     rax, [rbp+4Fh+Data]
0x18002dc30  mov     [rsp+110h+cbData], 48h ; 'H'; cbData
0x18002dc38  mov     [rsp+110h+lpData], rax; lpData
0x18002dc3d  mov     [rbp+4Fh+var_78], esi
0x18002dc40  mov     [rbp+4Fh+var_74], edi
0x18002dc43  mov     [rbp+4Fh+var_70], 0
0x18002dc4a  mov     [rbp+4Fh+var_6C], r15d
0x18002dc4e  movdqu  [rbp+4Fh+var_68], xmm0
0x18002dc53  mov     [rbp+4Fh+var_58], 0
0x18002dc5b  mov     [rbp+4Fh+var_50], 0
0x18002dc63  call    cs:__imp_RegSetValueExW
0x18002dc69  test    eax, eax
0x18002dc6b  jle     short loc_18002DC75
0x18002dc6d  movzx   eax, ax
0x18002dc70  or      eax, 80070000h
0x18002dc75  mov     [rbp+4Fh+var_C8], eax
0x18002dc78  test    eax, eax
0x18002dc7a  jns     short loc_18002DC86
0x18002dc7c  mov     ecx, 0E7h
0x18002dc81  jmp     loc_18002DBD3
0x18002dc86  mov     [rbp+4Fh+var_C8], 0
0x18002dc8d  mov     eax, 0E9h
0x18002dc92  xor     ebx, ebx
0x18002dc94  mov     [rbp+4Fh+var_C4], ax
0x18002dc98  lea     rcx, [rsp+110h+lpValueName]; this
0x18002dc9d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002dca2  lea     rcx, [rbp+4Fh+var_C8]; this
0x18002dca6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002dcab  mov     eax, ebx
0x18002dcad  mov     rcx, [rbp+4Fh+var_40]
0x18002dcb1  xor     rcx, rsp; StackCookie
0x18002dcb4  call    __security_check_cookie
0x18002dcb9  add     rsp, 0E0h
0x18002dcc0  pop     r15
0x18002dcc2  pop     r14
0x18002dcc4  pop     r12
0x18002dcc6  pop     rdi
0x18002dcc7  pop     rsi
0x18002dcc8  pop     rbx
0x18002dcc9  pop     rbp
0x18002dcca  retn
```
