# AssertPrivilege(ushort const *)

- ea: `0x18001bfcc`
- end: `0x18001c0cf`
- name: `?AssertPrivilege@@YAJPEBG@Z`
- size: `259`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014d1c`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001bfcc`
- `0x18001c0d8`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c031`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c043`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0ab`

## string_xrefs

- `0x18001c013`: `AssertPrivilege`

## pseudocode

```c
__int64 __fastcall AssertPrivilege(LPCWSTR lpName)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rcx
  int LastFailureAsHRESULT; // ebx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int16 v7; // [rsp+24h] [rbp-3Ch]
  __int16 v8; // [rsp+26h] [rbp-3Ah]
  int v9; // [rsp+28h] [rbp-38h]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "AssertPrivilege", 1239, 1);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
  {
    v7 = 1242;
    v6 = 0;
    LastFailureAsHRESULT = AssertPrivilegeOnToken(TokenHandle, lpName);
    v6 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v7 = 1243;
    }
    else
    {
      v8 = 1243;
      v9 = 1;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v3);
    v6 = LastFailureAsHRESULT;
    v8 = 1242;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001bfcc  mov     [rsp-8+arg_0], rbx
0x18001bfd1  push    rbp
0x18001bfd2  mov     rbp, rsp
0x18001bfd5  sub     rsp, 60h
0x18001bfd9  mov     rbx, rcx
0x18001bfdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfe3  lea     rax, WPP_GLOBAL_Control
0x18001bfea  cmp     rcx, rax
0x18001bfed  jz      short loc_18001C00D
0x18001bfef  test    dword ptr [rcx+1Ch], 20000000h
0x18001bff6  jz      short loc_18001C00D
0x18001bff8  mov     rcx, [rcx+10h]
0x18001bffc  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18001c003  mov     edx, 23h ; '#'
0x18001c008  call    WPP_SF_
0x18001c00d  mov     r9d, 1; unsigned __int16
0x18001c013  lea     rdx, aAssertprivileg; "AssertPrivilege"
0x18001c01a  mov     r8d, 4D7h; unsigned __int16
0x18001c020  lea     rcx, [rbp+var_40]; this
0x18001c024  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c029  mov     [rbp+TokenHandle], 0
0x18001c031  call    cs:__imp_GetCurrentProcess
0x18001c037  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001c03b  mov     edx, 2000000h; DesiredAccess
0x18001c040  mov     rcx, rax; ProcessHandle
0x18001c043  call    cs:__imp_OpenProcessToken
0x18001c049  test    eax, eax
0x18001c04b  jnz     short loc_18001C062
0x18001c04d  call    GetLastFailureAsHRESULT
0x18001c052  mov     ebx, eax
0x18001c054  mov     [rbp+var_40], eax
0x18001c057  mov     eax, 4DAh
0x18001c05c  mov     [rbp+var_3A], ax
0x18001c060  jmp     short loc_18001C09D
0x18001c062  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001c066  mov     eax, 4DAh
0x18001c06b  mov     rdx, rbx; lpName
0x18001c06e  mov     [rbp+var_3C], ax
0x18001c072  mov     [rbp+var_40], 0
0x18001c079  call    ?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z; AssertPrivilegeOnToken(void *,ushort const *)
0x18001c07e  mov     ebx, eax
0x18001c080  mov     [rbp+var_40], eax
0x18001c083  test    eax, eax
0x18001c085  mov     eax, 4DBh
0x18001c08a  jns     short loc_18001C099
0x18001c08c  mov     [rbp+var_3A], ax
0x18001c090  mov     [rbp+var_38], 1
0x18001c097  jmp     short loc_18001C09D
0x18001c099  mov     [rbp+var_3C], ax
0x18001c09d  mov     rcx, [rbp+TokenHandle]; hObject
0x18001c0a1  lea     rdx, [rcx-1]
0x18001c0a5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c0a9  ja      short loc_18001C0B9
0x18001c0ab  call    cs:__imp_CloseHandle
0x18001c0b1  mov     [rbp+TokenHandle], 0
0x18001c0b9  lea     rcx, [rbp+var_40]; this
0x18001c0bd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c0c2  mov     eax, ebx
0x18001c0c4  mov     rbx, [rsp+60h+arg_0]
0x18001c0c9  add     rsp, 60h
0x18001c0cd  pop     rbp
0x18001c0ce  retn
```
