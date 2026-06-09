# SxOpenThreadOrProcessToken(ulong,void * *)

- ea: `0x18000ef70`
- end: `0x18000f14b`
- name: `?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z`
- size: `475`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c6e0`
- `0x18000cc20`
- `0x18000e554`

## callees

- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x18000ef70`
- `0x18000f154`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f01c`
- `KERNEL32!GetLastError` at `0x18000f01c`
- `KERNEL32!CloseHandle` at `0x18000f05d`
- `KERNEL32!CloseHandle` at `0x18000f0b1`
- `KERNEL32!CloseHandle` at `0x18000f120`
- `KERNEL32!CloseHandle` at `0x18000f05d`
- `KERNEL32!CloseHandle` at `0x18000f0b1`
- `KERNEL32!CloseHandle` at `0x18000f120`
- `KERNEL32!GetCurrentProcess` at `0x18000f06b`
- `KERNEL32!GetCurrentProcess` at `0x18000f06b`
- `KERNEL32!GetCurrentThread` at `0x18000effa`
- `KERNEL32!GetCurrentThread` at `0x18000f0bf`
- `KERNEL32!GetCurrentThread` at `0x18000effa`
- `KERNEL32!GetCurrentThread` at `0x18000f0bf`
- `ADVAPI32!OpenProcessToken` at `0x18000f07d`
- `ADVAPI32!OpenProcessToken` at `0x18000f07d`
- `ADVAPI32!OpenThreadToken` at `0x18000f00e`
- `ADVAPI32!OpenThreadToken` at `0x18000f0d5`
- `ADVAPI32!OpenThreadToken` at `0x18000f00e`
- `ADVAPI32!OpenThreadToken` at `0x18000f0d5`

## string_xrefs

- `0x18000efbc`: `SxOpenThreadOrProcessToken`

## pseudocode

```c
__int64 __fastcall SxOpenThreadOrProcessToken(__int64 a1, void **a2)
{
  char *v3; // rdx
  __int64 v4; // r8
  signed int LastFailureAsHRESULT; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int16 v8; // ax
  HANDLE CurrentProcess; // rax
  HANDLE v10; // rax
  int v12; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxOpenThreadOrProcessToken", 600);
  TokenHandle = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = 605;
    v12 = -2147024809;
    goto LABEL_30;
  }
  v12 = 0;
  v13 = 605;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    LastFailureAsHRESULT = v12;
    goto LABEL_27;
  }
  LastError = GetLastError();
  LastFailureAsHRESULT = LastError;
  if ( LastError == 5 )
  {
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    v10 = GetCurrentThread();
    if ( !OpenThreadToken(v10, 0x28u, 1, &TokenHandle) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v12 = LastFailureAsHRESULT;
      v8 = 630;
      goto LABEL_17;
    }
    v8 = 630;
  }
  else
  {
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
      v12 = LastFailureAsHRESULT;
      v8 = 637;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_17;
      goto LABEL_25;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v12 = LastFailureAsHRESULT;
      v8 = 623;
LABEL_17:
      v14 = v8;
      goto LABEL_28;
    }
    v8 = 623;
  }
  LastFailureAsHRESULT = 0;
  v12 = 0;
LABEL_25:
  v13 = v8;
LABEL_27:
  *a2 = TokenHandle;
  TokenHandle = 0;
LABEL_28:
  v3 = (char *)TokenHandle - 1;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
LABEL_30:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, (__int64)v3, v4);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000ef70  mov     [rsp-8+arg_0], rbx
0x18000ef75  mov     [rsp-8+arg_10], rdi
0x18000ef7a  push    rbp
0x18000ef7b  mov     rbp, rsp
0x18000ef7e  sub     rsp, 60h
0x18000ef82  mov     rdi, rdx
0x18000ef85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef8c  lea     rax, WPP_GLOBAL_Control
0x18000ef93  cmp     rcx, rax
0x18000ef96  jz      short loc_18000EFB6
0x18000ef98  test    dword ptr [rcx+1Ch], 20000000h
0x18000ef9f  jz      short loc_18000EFB6
0x18000efa1  mov     rcx, [rcx+10h]
0x18000efa5  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000efac  mov     edx, 15h
0x18000efb1  call    WPP_SF_
0x18000efb6  mov     r8d, 258h; unsigned __int16
0x18000efbc  lea     rdx, aSxopenthreador; "SxOpenThreadOrProcessToken"
0x18000efc3  lea     rcx, [rbp+var_40]; this
0x18000efc7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000efcc  mov     [rbp+TokenHandle], 0
0x18000efd4  mov     eax, 25Dh
0x18000efd9  test    rdi, rdi
0x18000efdc  jnz     short loc_18000EFEF
0x18000efde  mov     ebx, 80070057h
0x18000efe3  mov     [rbp+var_3A], ax
0x18000efe7  mov     [rbp+var_40], ebx
0x18000efea  jmp     loc_18000F12E
0x18000efef  mov     [rbp+var_40], 0
0x18000eff6  mov     [rbp+var_3C], ax
0x18000effa  call    cs:__imp_GetCurrentThread
0x18000f000  xor     r8d, r8d; OpenAsSelf
0x18000f003  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000f007  mov     rcx, rax; ThreadHandle
0x18000f00a  lea     edx, [r8+28h]; DesiredAccess
0x18000f00e  call    cs:__imp_OpenThreadToken
0x18000f014  test    eax, eax
0x18000f016  jnz     loc_18000F100
0x18000f01c  call    cs:__imp_GetLastError
0x18000f022  mov     ebx, eax
0x18000f024  cmp     eax, 5
0x18000f027  jz      short loc_18000F0A3
0x18000f029  cmp     eax, 3F0h
0x18000f02e  jz      short loc_18000F04F
0x18000f030  test    eax, eax
0x18000f032  jle     short loc_18000F03D
0x18000f034  movzx   ebx, ax
0x18000f037  or      ebx, 80070000h
0x18000f03d  mov     [rbp+var_40], ebx
0x18000f040  mov     eax, 27Dh
0x18000f045  test    ebx, ebx
0x18000f047  jns     loc_18000F0FA
0x18000f04d  jmp     short loc_18000F096
0x18000f04f  mov     rcx, [rbp+TokenHandle]; hObject
0x18000f053  lea     rax, [rcx-1]
0x18000f057  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f05b  ja      short loc_18000F06B
0x18000f05d  call    cs:__imp_CloseHandle
0x18000f063  mov     [rbp+TokenHandle], 0
0x18000f06b  call    cs:__imp_GetCurrentProcess
0x18000f071  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000f075  mov     edx, 28h ; '('; DesiredAccess
0x18000f07a  mov     rcx, rax; ProcessHandle
0x18000f07d  call    cs:__imp_OpenProcessToken
0x18000f083  test    eax, eax
0x18000f085  jnz     short loc_18000F09C
0x18000f087  call    GetLastFailureAsHRESULT
0x18000f08c  mov     ebx, eax
0x18000f08e  mov     [rbp+var_40], eax
0x18000f091  mov     eax, 26Fh
0x18000f096  mov     [rbp+var_3A], ax
0x18000f09a  jmp     short loc_18000F112
0x18000f09c  mov     eax, 26Fh
0x18000f0a1  jmp     short loc_18000F0F5
0x18000f0a3  mov     rcx, [rbp+TokenHandle]; hObject
0x18000f0a7  lea     rax, [rcx-1]
0x18000f0ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f0af  ja      short loc_18000F0BF
0x18000f0b1  call    cs:__imp_CloseHandle
0x18000f0b7  mov     [rbp+TokenHandle], 0
0x18000f0bf  call    cs:__imp_GetCurrentThread
0x18000f0c5  mov     edx, 28h ; '('; DesiredAccess
0x18000f0ca  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000f0ce  mov     rcx, rax; ThreadHandle
0x18000f0d1  lea     r8d, [rdx-27h]; OpenAsSelf
0x18000f0d5  call    cs:__imp_OpenThreadToken
0x18000f0db  test    eax, eax
0x18000f0dd  jnz     short loc_18000F0F0
0x18000f0df  call    GetLastFailureAsHRESULT
0x18000f0e4  mov     ebx, eax
0x18000f0e6  mov     [rbp+var_40], eax
0x18000f0e9  mov     eax, 276h
0x18000f0ee  jmp     short loc_18000F096
0x18000f0f0  mov     eax, 276h
0x18000f0f5  xor     ebx, ebx
0x18000f0f7  mov     [rbp+var_40], ebx
0x18000f0fa  mov     [rbp+var_3C], ax
0x18000f0fe  jmp     short loc_18000F103
0x18000f100  mov     ebx, [rbp+var_40]
0x18000f103  mov     rax, [rbp+TokenHandle]
0x18000f107  mov     [rdi], rax
0x18000f10a  mov     [rbp+TokenHandle], 0
0x18000f112  mov     rcx, [rbp+TokenHandle]; hObject
0x18000f116  lea     rdx, [rcx-1]
0x18000f11a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000f11e  ja      short loc_18000F12E
0x18000f120  call    cs:__imp_CloseHandle
0x18000f126  mov     [rbp+TokenHandle], 0
0x18000f12e  lea     rcx, [rbp+var_40]; this
0x18000f132  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f137  lea     r11, [rsp+60h+var_s0]
0x18000f13c  mov     eax, ebx
0x18000f13e  mov     rbx, [r11+10h]
0x18000f142  mov     rdi, [r11+20h]
0x18000f146  mov     rsp, r11
0x18000f149  pop     rbp
0x18000f14a  retn
```
