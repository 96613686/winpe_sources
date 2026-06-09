# GetProcessSID(tagOCTET_STRING *)

- ea: `0x180010590`
- end: `0x180010703`
- name: `?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(struct tagOCTET_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180010590`
- `0x180012d62`
- `0x180012d6e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001068e`
- `KERNEL32!GetLastError` at `0x1800106bc`
- `KERNEL32!GetLastError` at `0x18001068e`
- `KERNEL32!GetLastError` at `0x1800106bc`
- `KERNEL32!CloseHandle` at `0x1800106ae`
- `KERNEL32!CloseHandle` at `0x1800106ae`
- `KERNEL32!GetCurrentThread` at `0x1800105e9`
- `KERNEL32!GetCurrentThread` at `0x1800105e9`
- `ADVAPI32!GetLengthSid` at `0x18001064e`
- `ADVAPI32!GetLengthSid` at `0x18001064e`
- `ADVAPI32!GetTokenInformation` at `0x18001063b`
- `ADVAPI32!GetTokenInformation` at `0x18001063b`
- `ADVAPI32!OpenThreadToken` at `0x180010605`
- `ADVAPI32!OpenThreadToken` at `0x180010605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800105c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001065e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800105c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001065e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106da`

## pseudocode

```c
__int64 __fastcall GetProcessSID(struct tagOCTET_STRING *a1)
{
  PSID *v3; // rax
  PSID *v4; // rdi
  HANDLE CurrentThread; // rax
  DWORD LengthSid; // ebp
  BYTE *v7; // rax
  unsigned int v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 )
    return 2147942487LL;
  TokenHandle = 0;
  v3 = (PSID *)CoTaskMemAlloc(0x4000u);
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x4000u);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, 0x4000u, &ReturnLength) )
      {
        LengthSid = GetLengthSid(*v4);
        v7 = (BYTE *)CoTaskMemAlloc(LengthSid);
        a1->lpValue = v7;
        if ( v7 )
        {
          v8 = 0;
          memcpy_0(v7, *v4, LengthSid);
          a1->dwLength = LengthSid;
        }
        else
        {
          v8 = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
    }
    CoTaskMemFree(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180010590  mov     [rsp+arg_10], rbx
0x180010595  mov     [rsp+arg_18], rbp
0x18001059a  push    rsi
0x18001059b  push    rdi
0x18001059c  push    r14
0x18001059e  sub     rsp, 30h
0x1800105a2  mov     rsi, rcx
0x1800105a5  test    rcx, rcx
0x1800105a8  jnz     short loc_1800105B4
0x1800105aa  mov     eax, 80070057h
0x1800105af  jmp     loc_1800106EF
0x1800105b4  mov     ebx, 4000h
0x1800105b9  mov     [rsp+48h+TokenHandle], 0
0x1800105c2  mov     ecx, ebx; cb
0x1800105c4  call    cs:__imp_CoTaskMemAlloc
0x1800105cb  nop     dword ptr [rax+rax+00h]
0x1800105d0  mov     rdi, rax
0x1800105d3  test    rax, rax
0x1800105d6  jz      loc_1800106E8
0x1800105dc  mov     r8d, ebx; Size
0x1800105df  xor     edx, edx; Val
0x1800105e1  mov     rcx, rax; void *
0x1800105e4  call    memset_0
0x1800105e9  call    cs:__imp_GetCurrentThread
0x1800105f0  nop     dword ptr [rax+rax+00h]
0x1800105f5  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800105fa  xor     r8d, r8d; OpenAsSelf
0x1800105fd  mov     rcx, rax; ThreadHandle
0x180010600  mov     edx, 20008h; DesiredAccess
0x180010605  call    cs:__imp_OpenThreadToken
0x18001060c  nop     dword ptr [rax+rax+00h]
0x180010611  test    eax, eax
0x180010613  jz      loc_1800106BC
0x180010619  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18001061e  lea     rax, [rsp+48h+arg_0]
0x180010623  mov     r9d, ebx; TokenInformationLength
0x180010626  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001062b  mov     r8, rdi; TokenInformation
0x18001062e  mov     [rsp+48h+arg_0], 0
0x180010636  mov     edx, 1; TokenInformationClass
0x18001063b  call    cs:__imp_GetTokenInformation
0x180010642  nop     dword ptr [rax+rax+00h]
0x180010647  test    eax, eax
0x180010649  jz      short loc_18001068E
0x18001064b  mov     rcx, [rdi]; pSid
0x18001064e  call    cs:__imp_GetLengthSid
0x180010655  nop     dword ptr [rax+rax+00h]
0x18001065a  mov     ecx, eax; cb
0x18001065c  mov     ebp, eax
0x18001065e  call    cs:__imp_CoTaskMemAlloc
0x180010665  nop     dword ptr [rax+rax+00h]
0x18001066a  mov     [rsi+8], rax
0x18001066e  test    rax, rax
0x180010671  jz      short loc_180010687
0x180010673  mov     rdx, [rdi]; Src
0x180010676  xor     ebx, ebx
0x180010678  mov     r8d, ebp; Size
0x18001067b  mov     rcx, rax; void *
0x18001067e  call    memcpy_0
0x180010683  mov     [rsi], ebp
0x180010685  jmp     short loc_1800106A9
0x180010687  mov     ebx, 8007000Eh
0x18001068c  jmp     short loc_1800106A9
0x18001068e  call    cs:__imp_GetLastError
0x180010695  nop     dword ptr [rax+rax+00h]
0x18001069a  mov     ebx, eax
0x18001069c  test    eax, eax
0x18001069e  jle     short loc_1800106A9
0x1800106a0  movzx   ebx, ax
0x1800106a3  or      ebx, 80070000h
0x1800106a9  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800106ae  call    cs:__imp_CloseHandle
0x1800106b5  nop     dword ptr [rax+rax+00h]
0x1800106ba  jmp     short loc_1800106D7
0x1800106bc  call    cs:__imp_GetLastError
0x1800106c3  nop     dword ptr [rax+rax+00h]
0x1800106c8  mov     ebx, eax
0x1800106ca  test    eax, eax
0x1800106cc  jle     short loc_1800106D7
0x1800106ce  movzx   ebx, ax
0x1800106d1  or      ebx, 80070000h
0x1800106d7  mov     rcx, rdi; pv
0x1800106da  call    cs:__imp_CoTaskMemFree
0x1800106e1  nop     dword ptr [rax+rax+00h]
0x1800106e6  jmp     short loc_1800106ED
0x1800106e8  mov     ebx, 8007000Eh
0x1800106ed  mov     eax, ebx
0x1800106ef  mov     rbx, [rsp+48h+arg_10]
0x1800106f4  mov     rbp, [rsp+48h+arg_18]
0x1800106f9  add     rsp, 30h
0x1800106fd  pop     r14
0x1800106ff  pop     rdi
0x180010700  pop     rsi
0x180010701  retn
```
