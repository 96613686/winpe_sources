# SxGetLastSystemRestoreId(CBsString *)

- ea: `0x18001e54c`
- end: `0x18001e676`
- name: `?SxGetLastSystemRestoreId@@YAJPEAVCBsString@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121bc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001e54c`
- `0x18001e7e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e640`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e640`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5e3`

## pseudocode

```c
__int64 __fastcall SxGetLastSystemRestoreId(struct CBsString *this)
{
  HKEY v2; // rcx
  __int16 v3; // ax
  _WORD *v4; // rcx
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int16 v8; // [rsp+34h] [rbp-3Ch]
  __int16 v9; // [rsp+36h] [rbp-3Ah]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "SxGetLastSystemRestoreId", 914, 2);
  v2 = 0;
  hKey = 0;
  if ( this )
  {
    if ( *((_DWORD *)this + 2) )
    {
      *((_DWORD *)this + 2) = 0;
      **(_WORD **)this = 0;
      v2 = hKey;
    }
    v7 = 0;
    v8 = 922;
    if ( (unsigned __int64)v2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v2);
      hKey = 0;
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
           0,
           0x20019u,
           &hKey) )
    {
      v3 = 937;
    }
    else
    {
      if ( (int)SxRegReadString(hKey, L"LastRestoreId", this) < 0 && *((_DWORD *)this + 2) )
      {
        v4 = *(_WORD **)this;
        *((_DWORD *)this + 2) = 0;
        *v4 = 0;
      }
      v3 = 953;
    }
    v8 = v3;
    v7 = 0;
    v5 = 0;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  else
  {
    v5 = -2147024809;
    v7 = -2147024809;
    v9 = 922;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18001e54c  mov     [rsp-8+arg_8], rbx
0x18001e551  push    rbp
0x18001e552  mov     rbp, rsp
0x18001e555  sub     rsp, 70h
0x18001e559  mov     rbx, rcx
0x18001e55c  lea     rdx, aSxgetlastsyste; "SxGetLastSystemRestoreId"
0x18001e563  lea     rcx, [rbp+var_40]; this
0x18001e567  mov     r9d, 2; unsigned __int16
0x18001e56d  mov     r8d, 392h; unsigned __int16
0x18001e573  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e578  xor     ecx, ecx
0x18001e57a  mov     [rbp+hKey], rcx
0x18001e57e  test    rbx, rbx
0x18001e581  jz      loc_18001E64C
0x18001e587  cmp     [rbx+8], ecx
0x18001e58a  jz      short loc_18001E59B
0x18001e58c  mov     [rbx+8], ecx
0x18001e58f  xor     eax, eax
0x18001e591  mov     rcx, [rbx]
0x18001e594  mov     [rcx], ax
0x18001e597  mov     rcx, [rbp+hKey]; hKey
0x18001e59b  mov     eax, 39Ah
0x18001e5a0  mov     [rbp+var_40], 0
0x18001e5a7  mov     [rbp+var_3C], ax
0x18001e5ab  lea     rax, [rcx-1]
0x18001e5af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e5b3  ja      short loc_18001E5C3
0x18001e5b5  call    cs:__imp_RegCloseKey
0x18001e5bb  mov     [rbp+hKey], 0
0x18001e5c3  lea     rax, [rbp+hKey]
0x18001e5c7  mov     r9d, 20019h; samDesired
0x18001e5cd  xor     r8d, r8d; ulOptions
0x18001e5d0  mov     [rsp+70h+phkResult], rax; phkResult
0x18001e5d5  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001e5dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e5e3  call    cs:__imp_RegOpenKeyExW
0x18001e5e9  test    eax, eax
0x18001e5eb  jz      short loc_18001E5F4
0x18001e5ed  mov     eax, 3A9h
0x18001e5f2  jmp     short loc_18001E625
0x18001e5f4  mov     rcx, [rbp+hKey]; hKey
0x18001e5f8  lea     rdx, aLastrestoreid; "LastRestoreId"
0x18001e5ff  mov     r8, rbx; this
0x18001e602  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18001e607  test    eax, eax
0x18001e609  jns     short loc_18001E620
0x18001e60b  cmp     dword ptr [rbx+8], 0
0x18001e60f  jz      short loc_18001E620
0x18001e611  mov     rcx, [rbx]
0x18001e614  xor     eax, eax
0x18001e616  mov     dword ptr [rbx+8], 0
0x18001e61d  mov     [rcx], ax
0x18001e620  mov     eax, 3B9h
0x18001e625  mov     [rbp+var_3C], ax
0x18001e629  mov     [rbp+var_40], 0
0x18001e630  mov     rcx, [rbp+hKey]; hKey
0x18001e634  xor     ebx, ebx
0x18001e636  lea     rax, [rcx-1]
0x18001e63a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e63e  ja      short loc_18001E65D
0x18001e640  call    cs:__imp_RegCloseKey
0x18001e646  mov     [rbp+hKey], rbx
0x18001e64a  jmp     short loc_18001E65D
0x18001e64c  mov     ebx, 80070057h
0x18001e651  mov     eax, 39Ah
0x18001e656  mov     [rbp+var_40], ebx
0x18001e659  mov     [rbp+var_3A], ax
0x18001e65d  lea     rcx, [rbp+var_40]; this
0x18001e661  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e666  mov     eax, ebx
0x18001e668  mov     rbx, [rsp+70h+arg_8]
0x18001e670  add     rsp, 70h
0x18001e674  pop     rbp
0x18001e675  retn
```
