# SxGetLastAsrRestoreId(CBsString *)

- ea: `0x18001e41c`
- end: `0x18001e546`
- name: `?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800120dc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001e41c`
- `0x18001e7e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e4b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e4b3`

## pseudocode

```c
__int64 __fastcall SxGetLastAsrRestoreId(struct CBsString *this)
{
  HKEY v2; // rcx
  __int16 v3; // ax
  _WORD *v4; // rcx
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int16 v8; // [rsp+34h] [rbp-3Ch]
  __int16 v9; // [rsp+36h] [rbp-3Ah]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "SxGetLastAsrRestoreId", 969, 2);
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
    v8 = 977;
    if ( (unsigned __int64)v2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v2);
      hKey = 0;
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
           0,
           0x20019u,
           &hKey) )
    {
      v3 = 992;
    }
    else
    {
      if ( (int)SxRegReadString(hKey, L"LastInstance", this) < 0 && *((_DWORD *)this + 2) )
      {
        v4 = *(_WORD **)this;
        *((_DWORD *)this + 2) = 0;
        *v4 = 0;
      }
      v3 = 1008;
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
    v9 = 977;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18001e41c  mov     [rsp-8+arg_8], rbx
0x18001e421  push    rbp
0x18001e422  mov     rbp, rsp
0x18001e425  sub     rsp, 70h
0x18001e429  mov     rbx, rcx
0x18001e42c  lea     rdx, aSxgetlastasrre; "SxGetLastAsrRestoreId"
0x18001e433  lea     rcx, [rbp+var_40]; this
0x18001e437  mov     r9d, 2; unsigned __int16
0x18001e43d  mov     r8d, 3C9h; unsigned __int16
0x18001e443  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e448  xor     ecx, ecx
0x18001e44a  mov     [rbp+hKey], rcx
0x18001e44e  test    rbx, rbx
0x18001e451  jz      loc_18001E51C
0x18001e457  cmp     [rbx+8], ecx
0x18001e45a  jz      short loc_18001E46B
0x18001e45c  mov     [rbx+8], ecx
0x18001e45f  xor     eax, eax
0x18001e461  mov     rcx, [rbx]
0x18001e464  mov     [rcx], ax
0x18001e467  mov     rcx, [rbp+hKey]; hKey
0x18001e46b  mov     eax, 3D1h
0x18001e470  mov     [rbp+var_40], 0
0x18001e477  mov     [rbp+var_3C], ax
0x18001e47b  lea     rax, [rcx-1]
0x18001e47f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e483  ja      short loc_18001E493
0x18001e485  call    cs:__imp_RegCloseKey
0x18001e48b  mov     [rbp+hKey], 0
0x18001e493  lea     rax, [rbp+hKey]
0x18001e497  mov     r9d, 20019h; samDesired
0x18001e49d  xor     r8d, r8d; ulOptions
0x18001e4a0  mov     [rsp+70h+phkResult], rax; phkResult
0x18001e4a5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\MICROSOFT\\WINDOWS NT\\Curren"...
0x18001e4ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e4b3  call    cs:__imp_RegOpenKeyExW
0x18001e4b9  test    eax, eax
0x18001e4bb  jz      short loc_18001E4C4
0x18001e4bd  mov     eax, 3E0h
0x18001e4c2  jmp     short loc_18001E4F5
0x18001e4c4  mov     rcx, [rbp+hKey]; hKey
0x18001e4c8  lea     rdx, aLastinstance; "LastInstance"
0x18001e4cf  mov     r8, rbx; this
0x18001e4d2  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18001e4d7  test    eax, eax
0x18001e4d9  jns     short loc_18001E4F0
0x18001e4db  cmp     dword ptr [rbx+8], 0
0x18001e4df  jz      short loc_18001E4F0
0x18001e4e1  mov     rcx, [rbx]
0x18001e4e4  xor     eax, eax
0x18001e4e6  mov     dword ptr [rbx+8], 0
0x18001e4ed  mov     [rcx], ax
0x18001e4f0  mov     eax, 3F0h
0x18001e4f5  mov     [rbp+var_3C], ax
0x18001e4f9  mov     [rbp+var_40], 0
0x18001e500  mov     rcx, [rbp+hKey]; hKey
0x18001e504  xor     ebx, ebx
0x18001e506  lea     rax, [rcx-1]
0x18001e50a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e50e  ja      short loc_18001E52D
0x18001e510  call    cs:__imp_RegCloseKey
0x18001e516  mov     [rbp+hKey], rbx
0x18001e51a  jmp     short loc_18001E52D
0x18001e51c  mov     ebx, 80070057h
0x18001e521  mov     eax, 3D1h
0x18001e526  mov     [rbp+var_40], ebx
0x18001e529  mov     [rbp+var_3A], ax
0x18001e52d  lea     rcx, [rbp+var_40]; this
0x18001e531  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e536  mov     eax, ebx
0x18001e538  mov     rbx, [rsp+70h+arg_8]
0x18001e540  add     rsp, 70h
0x18001e544  pop     rbp
0x18001e545  retn
```
