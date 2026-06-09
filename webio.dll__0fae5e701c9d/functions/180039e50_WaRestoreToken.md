# WaRestoreToken

- ea: `0x180039e50`
- end: `0x180039f34`
- name: `WaRestoreToken`
- size: `228`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f850`
- `0x18000ff50`
- `0x18001b780`
- `0x18001ec68`
- `0x180023410`
- `0x180024630`
- `0x180039210`
- `0x18003a020`
- `0x18004b5f4`
- `0x18004c10c`
- `0x180054808`
- `0x180057a90`
- `0x180057ee8`
- `0x180058314`
- `0x18005d3d8`
- `0x18005e068`
- `0x18005e5a8`
- `0x180060ea8`
- `0x180063854`
- `0x180063d28`
- `0x1800694c0`
- `0x18007688c`
- `0x1800826dc`
- `0x180082824`
- `0x1800829c0`

## callees

- `0x1800180e0`
- `0x18002e460`
- `0x180039e50`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180039e82`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180039e82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e9e`

## pseudocode

```c
__int64 __fastcall WaRestoreToken(HANDLE hObject)
{
  __int64 result; // rax
  unsigned int LastError; // edi
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // [rsp+30h] [rbp-58h] BYREF
  HANDLE v7; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v8[16]; // [rsp+40h] [rbp-48h] BYREF
  HANDLE *v9; // [rsp+50h] [rbp-38h]
  __int64 v10; // [rsp+58h] [rbp-30h]
  int *v11; // [rsp+60h] [rbp-28h]
  __int64 v12; // [rsp+68h] [rbp-20h]

  result = 0;
  if ( hObject != (HANDLE)-1LL )
  {
    LastError = 0;
    if ( !SetThreadToken(0, hObject) )
      LastError = WaGetLastError(v4);
    if ( hObject )
      CloseHandle(hObject);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v6 = LastError;
      v9 = &v7;
      v7 = hObject;
      v11 = (int *)&v6;
      v10 = 8;
      v12 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenRestore, v5, 3, v8);
    }
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180039e50  push    rbx
0x180039e52  sub     rsp, 80h
0x180039e59  mov     rax, cs:__security_cookie
0x180039e60  xor     rax, rsp
0x180039e63  mov     [rsp+88h+var_18], rax
0x180039e68  xor     eax, eax
0x180039e6a  mov     rbx, rcx
0x180039e6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180039e71  jz      short loc_180039EBD
0x180039e73  mov     rdx, rcx; Token
0x180039e76  mov     [rsp+88h+arg_8], rdi
0x180039e7e  xor     ecx, ecx; Thread
0x180039e80  xor     edi, edi
0x180039e82  call    cs:__imp_SetThreadToken
0x180039e89  nop     dword ptr [rax+rax+00h]
0x180039e8e  test    eax, eax
0x180039e90  jz      loc_180039F28
0x180039e96  test    rbx, rbx
0x180039e99  jz      short loc_180039EAA
0x180039e9b  mov     rcx, rbx; hObject
0x180039e9e  call    cs:__imp_CloseHandle
0x180039ea5  nop     dword ptr [rax+rax+00h]
0x180039eaa  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180039eb1  jnz     short loc_180039ED4
0x180039eb3  mov     eax, edi
0x180039eb5  mov     rdi, [rsp+88h+arg_8]
0x180039ebd  mov     rcx, [rsp+88h+var_18]
0x180039ec2  xor     rcx, rsp; StackCookie
0x180039ec5  call    __security_check_cookie
0x180039eca  add     rsp, 80h
0x180039ed1  pop     rbx
0x180039ed2  retn
0x180039ed4  lea     rax, [rsp+88h+var_50]
0x180039ed9  mov     [rsp+88h+var_58], edi
0x180039edd  mov     [rsp+88h+var_38], rax
0x180039ee2  lea     rdx, ThreadTokenRestore
0x180039ee9  lea     rax, [rsp+88h+var_58]
0x180039eee  mov     [rsp+88h+var_50], rbx
0x180039ef3  mov     [rsp+88h+var_28], rax
0x180039ef8  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180039eff  lea     rax, [rsp+88h+var_48]
0x180039f04  mov     [rsp+88h+var_30], 8
0x180039f0d  mov     r9d, 3
0x180039f13  mov     [rsp+88h+var_68], rax
0x180039f18  mov     [rsp+88h+var_20], 4
0x180039f21  call    McGenEventWrite_EventWriteTransfer
0x180039f26  jmp     short loc_180039EB3
0x180039f28  call    WaGetLastError
0x180039f2d  mov     edi, eax
0x180039f2f  jmp     loc_180039E96
```
