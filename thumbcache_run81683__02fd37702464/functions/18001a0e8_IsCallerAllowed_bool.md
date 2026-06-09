# IsCallerAllowed(bool)

- ea: `0x18001a0e8`
- end: `0x18001a1fb`
- name: `?IsCallerAllowed@@YA_N_N@Z`
- size: `275`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019980`
- `0x18002ff10`
- `0x18003cfc0`
- `0x18003d6b0`
- `0x18003e890`

## callees

- `0x18001a0e8`
- `0x18001a204`
- `0x18001a320`
- `0x18001a548`
- `0x18002c3b0`
- `0x18002d69c`
- `0x180035830`
- `0x180045eb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a163`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsCallerAllowed(__int64 a1, __int64 a2)
{
  bool v2; // bl
  int CallingProcessHandle; // eax
  unsigned __int16 **v4; // r8
  int v5; // ecx
  int PackageFamilyNameFromProcess; // eax
  bool *v7; // r8
  CallerIdentity *v8; // rcx
  bool *v9; // r8
  char *v10; // rcx
  unsigned __int16 v12; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv[3]; // [rsp+28h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF

  v2 = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(a1, a2, &hObject);
  v5 = 0;
  if ( CallingProcessHandle < 0 )
    v5 = CallingProcessHandle;
  if ( v5 >= 0 )
  {
    pv[0] = 0;
    pv[1] = (LPVOID)-1LL;
    pv[2] = (LPVOID)-1LL;
    PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(hObject, pv, v4);
    if ( PackageFamilyNameFromProcess < 0 )
    {
      if ( PackageFamilyNameFromProcess == -2147009196 )
      {
        LOBYTE(v12) = 0;
        if ( (int)CallerIdentity::IsProcessAppContainer((CallerIdentity *)hObject, &v12, v7) >= 0 && !(_BYTE)v12 )
          v2 = (unsigned int)IsProcessLowIL(hObject) == 1;
      }
    }
    else
    {
      v2 = 1;
      if ( !IsProcessPhotosApp((LPCWCH)pv[0]) )
      {
        LOBYTE(v12) = 0;
        if ( CallerIdentity::CheckCallerCapability(v8, &v12, v9) < 0 || !(_BYTE)v12 )
          v2 = 0;
      }
    }
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
  }
  v10 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  return v2;
}

```

## disassembly

```asm
0x18001a0e8  mov     [rsp-8+arg_0], rbx
0x18001a0ed  push    rbp
0x18001a0ee  mov     rbp, rsp
0x18001a0f1  sub     rsp, 50h
0x18001a0f5  mov     rax, cs:__security_cookie
0x18001a0fc  xor     rax, rsp
0x18001a0ff  mov     [rbp+var_8], rax
0x18001a103  xor     bl, bl
0x18001a105  mov     [rbp+hObject], 0
0x18001a10d  lea     r8, [rbp+hObject]
0x18001a111  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18001a116  xor     ecx, ecx
0x18001a118  test    eax, eax
0x18001a11a  cmovs   ecx, eax
0x18001a11d  test    ecx, ecx
0x18001a11f  js      short loc_18001A16A
0x18001a121  mov     [rbp+pv], 0
0x18001a129  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a12d  mov     [rbp+var_20], rax
0x18001a131  mov     [rbp+var_18], rax
0x18001a135  lea     rdx, [rbp+pv]; void *
0x18001a139  mov     rcx, [rbp+hObject]; hProcess
0x18001a13d  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x18001a142  test    eax, eax
0x18001a144  js      short loc_18001A1B4
0x18001a146  mov     rcx, [rbp+pv]; lpString2
0x18001a14a  call    ?IsProcessPhotosApp@@YA_NPEBG@Z; IsProcessPhotosApp(ushort const *)
0x18001a14f  test    al, al
0x18001a151  jz      short loc_18001A199
0x18001a153  mov     ebx, 1
0x18001a158  cmp     [rbp+pv], 0
0x18001a15d  jz      short loc_18001A16A
0x18001a15f  mov     rcx, [rbp+pv]; pv
0x18001a163  call    cs:__imp_CoTaskMemFree
0x18001a169  nop
0x18001a16a  mov     rcx, [rbp+hObject]; hObject
0x18001a16e  mov     [rbp+hObject], 0
0x18001a176  lea     rdx, [rcx-1]
0x18001a17a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a17e  jbe     short loc_18001A1F3
0x18001a180  mov     al, bl
0x18001a182  mov     rcx, [rbp+var_8]
0x18001a186  xor     rcx, rsp; StackCookie
0x18001a189  call    __security_check_cookie
0x18001a18e  mov     rbx, [rsp+50h+arg_0]
0x18001a193  add     rsp, 50h
0x18001a197  pop     rbp
0x18001a198  retn
0x18001a199  mov     byte ptr [rbp+var_30], 0
0x18001a19d  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18001a1a1  call    ?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z; CallerIdentity::CheckCallerCapability(ushort const *,bool *)
0x18001a1a6  test    eax, eax
0x18001a1a8  js      short loc_18001A1B0
0x18001a1aa  cmp     byte ptr [rbp+var_30], 0
0x18001a1ae  jnz     short loc_18001A153
0x18001a1b0  xor     bl, bl
0x18001a1b2  jmp     short loc_18001A158
0x18001a1b4  cmp     eax, 80073D54h
0x18001a1b9  jnz     short loc_18001A158
0x18001a1bb  mov     byte ptr [rbp+var_30], 0
0x18001a1bf  lea     rdx, [rbp+var_30]; void *
0x18001a1c3  mov     rcx, [rbp+hObject]; this
0x18001a1c7  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18001a1cc  test    eax, eax
0x18001a1ce  js      short loc_18001A158
0x18001a1d0  cmp     byte ptr [rbp+var_30], 0
0x18001a1d4  jnz     short loc_18001A158
0x18001a1d6  mov     rcx, [rbp+hObject]; void *
0x18001a1da  call    ?IsProcessLowIL@@YAJPEAX@Z; IsProcessLowIL(void *)
0x18001a1df  movzx   edx, bl
0x18001a1e2  mov     ebx, 1
0x18001a1e7  cmp     eax, ebx
0x18001a1e9  cmovz   edx, ebx
0x18001a1ec  mov     bl, dl
0x18001a1ee  jmp     loc_18001A158
0x18001a1f3  call    cs:__imp_CloseHandle
0x18001a1f9  jmp     short loc_18001A180
```
