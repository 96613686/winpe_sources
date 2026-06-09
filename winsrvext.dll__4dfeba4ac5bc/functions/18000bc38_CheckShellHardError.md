# CheckShellHardError

- ea: `0x18000bc38`
- end: `0x18000bee3`
- name: `CheckShellHardError`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d030`

## callees

- `0x18000bc38`
- `0x1800138ad`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000bd94`
- `KERNELBASE!LocalAlloc` at `0x18000bd94`
- `ntdll!NtQueryValueKey` at `0x18000bd29`
- `ntdll!NtQueryValueKey` at `0x18000bd29`
- `ntdll!NtOpenKey` at `0x18000bcdb`
- `ntdll!NtOpenKey` at `0x18000bcdb`
- `ntdll!RtlInitUnicodeString` at `0x18000bca1`
- `ntdll!RtlInitUnicodeString` at `0x18000bcfc`
- `ntdll!RtlInitUnicodeString` at `0x18000bca1`
- `ntdll!RtlInitUnicodeString` at `0x18000bcfc`
- `ntdll!NtClose` at `0x18000bd3f`
- `ntdll!NtClose` at `0x18000bd3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bea8`
- `USER32!GetTaskmanWindow` at `0x18000bd57`
- `USER32!GetTaskmanWindow` at `0x18000bd57`
- `USER32!RegisterWindowMessageW` at `0x18000bdcc`
- `USER32!RegisterWindowMessageW` at `0x18000bdcc`
- `USER32!SendMessageTimeoutW` at `0x18000be83`
- `USER32!SendMessageTimeoutW` at `0x18000be83`

## string_xrefs

- `0x18000bc96`: `\Registry\Machine\System\CurrentControlSet\Control\Windows`

## pseudocode

```c
__int64 __fastcall CheckShellHardError(__int64 a1, _DWORD *a2)
{
  bool v2; // zf
  int v5; // ebx
  unsigned int v6; // r15d
  HWND TaskmanWindow; // r12
  int v8; // ebx
  __int64 v9; // rbx
  _DWORD *v10; // rsi
  UINT v11; // eax
  const void *v12; // rdx
  char *v13; // rdi
  unsigned __int64 v14; // rbx
  ULONG ResultLength; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-75h]
  unsigned int v18; // [rsp+48h] [rbp-71h]
  void *KeyHandle; // [rsp+50h] [rbp-69h] BYREF
  ULONG_PTR dwResult; // [rsp+58h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-59h] BYREF
  LPARAM lParam[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v23; // [rsp+80h] [rbp-39h]
  _DWORD *v24; // [rsp+88h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+C0h] [rbp+7h] BYREF
  int v27; // [rsp+CCh] [rbp+13h]

  KeyHandle = 0;
  v2 = (*(_DWORD *)(a1 + 136) & 0x100) == 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( v2 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Windows");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  v5 = 0;
  RtlInitUnicodeString(&DestinationString, L"ShellErrorMode");
  if ( NtQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x14u,
         &ResultLength) >= 0 )
    v5 = v27;
  NtClose(KeyHandle);
  if ( v5 != 1 )
    return 0;
  v6 = 0;
  TaskmanWindow = (HWND)GetTaskmanWindow();
  if ( TaskmanWindow )
  {
    v8 = *(unsigned __int16 *)(a1 + 160);
    v18 = *(unsigned __int16 *)(a1 + 144) + 2;
    v9 = (unsigned int)(v8 + 2);
    v17 = v9 + v18 + 20;
    v24 = LocalAlloc(0x40u, v17);
    v10 = v24;
    if ( v24 )
    {
      v23 = 0;
      *(_OWORD *)lParam = 0;
      dwResult = 0;
      v11 = RegisterWindowMessageW(L"HardError");
      *v10 = 20;
      lParam[0] = v11;
      LODWORD(lParam[1]) = v17;
      HIDWORD(v23) = HIDWORD(v24);
      v10[1] = *(_DWORD *)(a1 + 64);
      v10[2] = *(_DWORD *)(a1 + 176);
      v10[4] = 0;
      v10[3] = 20;
      v12 = *(const void **)(a1 + 168);
      LODWORD(v23) = (_DWORD)v10;
      memcpy_0(v10 + 5, v12, v9 - 2);
      *((_WORD *)v10 + ((unsigned __int64)(unsigned int)v9 >> 1) + 9) = 0;
      v13 = (char *)v10 + v9 + 20;
      v14 = v18;
      v10[4] = (_DWORD)v13 - (_DWORD)v10;
      memcpy_0(v13, *(const void **)(a1 + 152), v14 - 2);
      dwResult = 0;
      *(_WORD *)&v13[2 * (v14 >> 1) - 2] = 0;
      if ( (unsigned int)SendMessageTimeoutW(TaskmanWindow, 0x4Au, 0, (LPARAM)lParam, 2u, 0xBB8u, &dwResult) )
      {
        if ( dwResult )
        {
          v6 = 1;
          *a2 = 1;
        }
      }
      LocalFree(v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000bc38  mov     [rsp-8+arg_10], rbx
0x18000bc3d  push    rbp
0x18000bc3e  push    rsi
0x18000bc3f  push    rdi
0x18000bc40  push    r12
0x18000bc42  push    r13
0x18000bc44  push    r14
0x18000bc46  push    r15
0x18000bc48  lea     rbp, [rsp-27h]
0x18000bc4d  sub     rsp, 0E0h
0x18000bc54  mov     rax, cs:__security_cookie
0x18000bc5b  xor     rax, rsp
0x18000bc5e  mov     [rbp+57h+var_38], rax
0x18000bc62  xorps   xmm0, xmm0
0x18000bc65  xor     edi, edi
0x18000bc67  xor     eax, eax
0x18000bc69  mov     [rbp+57h+KeyHandle], rdi
0x18000bc6d  test    dword ptr [rcx+88h], 100h
0x18000bc77  mov     r13, rdx
0x18000bc7a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000bc7e  mov     r14, rcx
0x18000bc81  mov     [rbp+57h+var_D0], edi
0x18000bc84  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000bc88  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000bc8c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000bc90  jz      loc_18000BEB9
0x18000bc96  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000bc9d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000bca1  call    cs:__imp_RtlInitUnicodeString
0x18000bca8  nop     dword ptr [rax+rax+00h]
0x18000bcad  lea     rax, [rbp+57h+DestinationString]
0x18000bcb1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000bcb8  xorps   xmm0, xmm0
0x18000bcbb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000bcbf  lea     esi, [rdi+40h]
0x18000bcc2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000bcc6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000bcca  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x18000bccd  mov     edx, 20019h; DesiredAccess
0x18000bcd2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000bcd6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bcdb  call    cs:__imp_NtOpenKey
0x18000bce2  nop     dword ptr [rax+rax+00h]
0x18000bce7  test    eax, eax
0x18000bce9  js      loc_18000BEB9
0x18000bcef  lea     rdx, aShellerrormode; "ShellErrorMode"
0x18000bcf6  mov     ebx, edi
0x18000bcf8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000bcfc  call    cs:__imp_RtlInitUnicodeString
0x18000bd03  nop     dword ptr [rax+rax+00h]
0x18000bd08  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000bd0c  lea     rax, [rbp+57h+var_D0]
0x18000bd10  mov     [rsp+110h+ResultLength], rax; ResultLength
0x18000bd15  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000bd19  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18000bd1d  mov     [rsp+110h+Length], 14h; Length
0x18000bd25  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000bd29  call    cs:__imp_NtQueryValueKey
0x18000bd30  nop     dword ptr [rax+rax+00h]
0x18000bd35  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000bd39  test    eax, eax
0x18000bd3b  cmovns  ebx, [rbp+57h+var_44]
0x18000bd3f  call    cs:__imp_NtClose
0x18000bd46  nop     dword ptr [rax+rax+00h]
0x18000bd4b  cmp     ebx, 1
0x18000bd4e  jnz     loc_18000BEB9
0x18000bd54  mov     r15d, edi
0x18000bd57  call    cs:__imp_GetTaskmanWindow
0x18000bd5e  nop     dword ptr [rax+rax+00h]
0x18000bd63  mov     r12, rax
0x18000bd66  test    rax, rax
0x18000bd69  jz      loc_18000BEB4
0x18000bd6f  movzx   eax, word ptr [r14+90h]
0x18000bd77  mov     ecx, esi; uFlags
0x18000bd79  movzx   ebx, word ptr [r14+0A0h]
0x18000bd81  add     eax, 2
0x18000bd84  mov     [rbp+57h+var_C8], eax
0x18000bd87  add     ebx, 2
0x18000bd8a  add     eax, 14h
0x18000bd8d  add     eax, ebx
0x18000bd8f  mov     edx, eax; uBytes
0x18000bd91  mov     [rbp+57h+var_CC], eax
0x18000bd94  call    cs:__imp_LocalAlloc
0x18000bd9b  nop     dword ptr [rax+rax+00h]
0x18000bda0  mov     [rbp+57h+var_88], rax
0x18000bda4  mov     rsi, rax
0x18000bda7  test    rax, rax
0x18000bdaa  jz      loc_18000BEB4
0x18000bdb0  xor     eax, eax
0x18000bdb2  lea     rcx, String; "HardError"
0x18000bdb9  xorps   xmm0, xmm0
0x18000bdbc  mov     [rbp+57h+var_90], rax
0x18000bdc0  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18000bdc4  mov     [rbp+57h+dwResult], rax
0x18000bdc8  lea     rdi, [rsi+14h]
0x18000bdcc  call    cs:__imp_RegisterWindowMessageW
0x18000bdd3  nop     dword ptr [rax+rax+00h]
0x18000bdd8  mov     dword ptr [rsi], 14h
0x18000bdde  lea     r8, [rbx-2]; Size
0x18000bde2  mov     eax, eax
0x18000bde4  mov     rcx, rdi; void *
0x18000bde7  mov     [rbp+57h+lParam], rax
0x18000bdeb  mov     eax, [rbp+57h+var_CC]
0x18000bdee  mov     dword ptr [rbp+57h+lParam+8], eax
0x18000bdf1  mov     eax, dword ptr [rbp+57h+var_88+4]
0x18000bdf4  mov     dword ptr [rbp+57h+var_90+4], eax
0x18000bdf7  mov     eax, [r14+40h]
0x18000bdfb  mov     [rsi+4], eax
0x18000bdfe  mov     eax, [r14+0B0h]
0x18000be05  mov     [rsi+8], eax
0x18000be08  mov     eax, edi
0x18000be0a  sub     eax, esi
0x18000be0c  mov     [rsi+10h], r15d
0x18000be10  mov     [rsi+0Ch], eax
0x18000be13  mov     rdx, [r14+0A8h]; Src
0x18000be1a  mov     dword ptr [rbp+57h+var_90], esi
0x18000be1d  call    memcpy_0
0x18000be22  xor     eax, eax
0x18000be24  mov     ecx, ebx
0x18000be26  shr     rcx, 1
0x18000be29  mov     [rdi+rcx*2-2], ax
0x18000be2e  add     rdi, rbx
0x18000be31  mov     ebx, [rbp+57h+var_C8]
0x18000be34  mov     eax, edi
0x18000be36  sub     eax, esi
0x18000be38  mov     rcx, rdi; void *
0x18000be3b  mov     [rsi+10h], eax
0x18000be3e  mov     rdx, [r14+98h]; Src
0x18000be45  lea     r8, [rbx-2]; Size
0x18000be49  call    memcpy_0
0x18000be4e  xor     eax, eax
0x18000be50  shr     rbx, 1
0x18000be53  xor     r8d, r8d; wParam
0x18000be56  mov     [rbp+57h+dwResult], rax
0x18000be5a  lea     r9, [rbp+57h+lParam]; lParam
0x18000be5e  mov     rcx, r12; hWnd
0x18000be61  mov     [rdi+rbx*2-2], ax
0x18000be66  lea     rax, [rbp+57h+dwResult]
0x18000be6a  mov     [rsp+110h+lpdwResult], rax; lpdwResult
0x18000be6f  lea     edx, [r8+4Ah]; Msg
0x18000be73  mov     dword ptr [rsp+110h+ResultLength], 0BB8h; uTimeout
0x18000be7b  mov     [rsp+110h+Length], 2; fuFlags
0x18000be83  call    cs:__imp_SendMessageTimeoutW
0x18000be8a  nop     dword ptr [rax+rax+00h]
0x18000be8f  test    eax, eax
0x18000be91  jz      short loc_18000BEA5
0x18000be93  cmp     [rbp+57h+dwResult], r15
0x18000be97  jz      short loc_18000BEA5
0x18000be99  mov     eax, 1
0x18000be9e  mov     r15d, eax
0x18000bea1  mov     [r13+0], eax
0x18000bea5  mov     rcx, rsi; hMem
0x18000bea8  call    cs:__imp_LocalFree
0x18000beaf  nop     dword ptr [rax+rax+00h]
0x18000beb4  mov     eax, r15d
0x18000beb7  jmp     short loc_18000BEBB
0x18000beb9  xor     eax, eax
0x18000bebb  mov     rcx, [rbp+57h+var_38]
0x18000bebf  xor     rcx, rsp; StackCookie
0x18000bec2  call    __security_check_cookie
0x18000bec7  mov     rbx, [rsp+110h+arg_10]
0x18000becf  add     rsp, 0E0h
0x18000bed6  pop     r15
0x18000bed8  pop     r14
0x18000beda  pop     r13
0x18000bedc  pop     r12
0x18000bede  pop     rdi
0x18000bedf  pop     rsi
0x18000bee0  pop     rbp
0x18000bee1  retn
```
