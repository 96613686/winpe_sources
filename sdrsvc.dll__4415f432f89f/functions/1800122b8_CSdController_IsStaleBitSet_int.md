# CSdController::_IsStaleBitSet(int *)

- ea: `0x1800122b8`
- end: `0x1800123ff`
- name: `?_IsStaleBitSet@CSdController@@AEAAJPEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(CSdController *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012408`

## callees

- `0x1800122b8`
- `0x18001586c`
- `0x180015974`
- `0x18001b544`
- `0x18001e67c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012352`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800123db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800123db`

## pseudocode

```c
__int64 __fastcall CSdController::_IsStaleBitSet(CSdController *this, int *a2)
{
  signed int DWORD; // ebx
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  __int16 v8; // ax
  int v10; // [rsp+50h] [rbp+7h] BYREF
  __int16 v11; // [rsp+54h] [rbp+Bh]
  __int16 v12; // [rsp+56h] [rbp+Dh]
  CSdController *v13; // [rsp+B0h] [rbp+67h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+77h] BYREF

  v13 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CSdController::_IsStaleBitSet", 1581, 1);
  hKey = 0;
  dwDisposition = 0;
  LODWORD(v13) = 0;
  if ( a2 )
  {
    v11 = 1587;
    v10 = 0;
    *a2 = 0;
    v4 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           &dwDisposition);
    DWORD = v4;
    if ( v4 > 0 )
      DWORD = (unsigned __int16)v4 | 0x80070000;
    v10 = DWORD;
    v8 = 1599;
    if ( DWORD < 0 )
      goto LABEL_6;
    v11 = 1599;
    DWORD = SetRegKeyVirtualization(hKey, v5, v6, v7);
    v10 = DWORD;
    v8 = 1600;
    if ( DWORD < 0
      || (v11 = 1600,
          DWORD = SxRegReadDWORD(hKey, L"BackupFlags", (unsigned int *)&v13, 0),
          v10 = DWORD,
          v8 = 1602,
          DWORD < 0) )
    {
LABEL_6:
      v12 = v8;
    }
    else
    {
      v11 = 1602;
      if ( ((unsigned __int8)v13 & 0x20) != 0 )
        *a2 = 1;
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  else
  {
    DWORD = -2147024809;
    v12 = 1587;
    v10 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)DWORD;
}

```

## disassembly

```asm
0x1800122b8  mov     [rsp-8+arg_0], rcx
0x1800122bd  push    rbp
0x1800122be  push    rbx
0x1800122bf  push    rdi
0x1800122c0  lea     rbp, [rsp-47h]
0x1800122c5  sub     rsp, 90h
0x1800122cc  mov     rdi, rdx
0x1800122cf  lea     rcx, [rbp+57h+var_50]; this
0x1800122d3  lea     rdx, aCsdcontrollerI; "CSdController::_IsStaleBitSet"
0x1800122da  mov     r9d, 1; unsigned __int16
0x1800122e0  mov     r8d, 62Dh; unsigned __int16
0x1800122e6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800122eb  xor     ecx, ecx
0x1800122ed  mov     eax, 633h
0x1800122f2  mov     [rbp+57h+hKey], rcx
0x1800122f6  mov     [rbp+57h+dwDisposition], ecx
0x1800122f9  mov     dword ptr [rbp+57h+arg_0], ecx
0x1800122fc  test    rdi, rdi
0x1800122ff  jnz     short loc_180012312
0x180012301  mov     ebx, 80070057h
0x180012306  mov     [rbp+57h+var_4A], ax
0x18001230a  mov     [rbp+57h+var_50], ebx
0x18001230d  jmp     loc_1800123E9
0x180012312  mov     [rbp+57h+var_4C], ax
0x180012316  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001231d  mov     [rbp+57h+var_50], ecx
0x180012320  lea     rax, [rbp+57h+dwDisposition]
0x180012324  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x180012329  xor     r9d, r9d; lpClass
0x18001232c  lea     rax, [rbp+57h+hKey]
0x180012330  mov     [rdi], ecx
0x180012332  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180012337  xor     r8d, r8d; Reserved
0x18001233a  mov     [rsp+0A0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18001233f  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x180012347  mov     [rsp+0A0h+dwOptions], ecx; dwOptions
0x18001234b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012352  call    cs:__imp_RegCreateKeyExW
0x180012358  mov     ebx, eax
0x18001235a  test    eax, eax
0x18001235c  jle     short loc_180012367
0x18001235e  movzx   ebx, ax
0x180012361  or      ebx, 80070000h
0x180012367  mov     [rbp+57h+var_50], ebx
0x18001236a  mov     eax, 63Fh
0x18001236f  test    ebx, ebx
0x180012371  jns     short loc_180012379
0x180012373  mov     [rbp+57h+var_4A], ax
0x180012377  jmp     short loc_1800123CD
0x180012379  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18001237d  mov     [rbp+57h+var_4C], ax
0x180012381  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x180012386  mov     ebx, eax
0x180012388  mov     [rbp+57h+var_50], eax
0x18001238b  test    eax, eax
0x18001238d  mov     eax, 640h
0x180012392  js      short loc_180012373
0x180012394  mov     rcx, [rbp+57h+hKey]; hKey
0x180012398  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x18001239c  xor     r9d, r9d; int
0x18001239f  mov     [rbp+57h+var_4C], ax
0x1800123a3  lea     rdx, c_wszSafedocsScheduleBackupFlags; "BackupFlags"
0x1800123aa  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800123af  mov     ebx, eax
0x1800123b1  mov     [rbp+57h+var_50], eax
0x1800123b4  test    eax, eax
0x1800123b6  mov     eax, 642h
0x1800123bb  js      short loc_180012373
0x1800123bd  test    byte ptr [rbp+57h+arg_0], 20h
0x1800123c1  mov     [rbp+57h+var_4C], ax
0x1800123c5  jz      short loc_1800123CD
0x1800123c7  mov     dword ptr [rdi], 1
0x1800123cd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800123d1  lea     rdx, [rcx-1]
0x1800123d5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800123d9  ja      short loc_1800123E9
0x1800123db  call    cs:__imp_RegCloseKey
0x1800123e1  mov     [rbp+57h+hKey], 0
0x1800123e9  lea     rcx, [rbp+57h+var_50]; this
0x1800123ed  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800123f2  mov     eax, ebx
0x1800123f4  add     rsp, 90h
0x1800123fb  pop     rdi
0x1800123fc  pop     rbx
0x1800123fd  pop     rbp
0x1800123fe  retn
```
