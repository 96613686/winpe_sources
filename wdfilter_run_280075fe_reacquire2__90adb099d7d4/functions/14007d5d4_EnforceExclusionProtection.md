# EnforceExclusionProtection

- ea: `0x14007d5d4`
- end: `0x14007d7bb`
- name: `EnforceExclusionProtection`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004da60`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x14007d5d4`
- `0x14007d7bc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14007d69c`
- `ntoskrnl!ZwOpenKey` at `0x14007d6e5`
- `ntoskrnl!ZwOpenKey` at `0x14007d69c`
- `ntoskrnl!ZwOpenKey` at `0x14007d6e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007d635`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007d635`
- `ntoskrnl!ZwClose` at `0x14007d77a`
- `ntoskrnl!ZwClose` at `0x14007d78f`
- `ntoskrnl!ZwClose` at `0x14007d77a`
- `ntoskrnl!ZwClose` at `0x14007d78f`

## string_xrefs

- `0x14007d614`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows Defender`

## pseudocode

```c
__int64 __fastcall EnforceExclusionProtection(struct _UNICODE_STRING *a1)
{
  NTSTATUS v3; // ebx
  __int64 v4; // rdx
  void *KeyHandle; // [rsp+30h] [rbp-39h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES v8; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp+37h] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  KeyHandle = 0;
  *(&v8.Length + 1) = 0;
  DestinationString = 0;
  *(&v8.Attributes + 1) = 0;
  Handle = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows Defender");
  if ( !a1 )
    return 3221225485LL;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  v8.Length = 48;
  v8.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  v8.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8.ObjectName = a1;
  *(_OWORD *)&v8.SecurityDescriptor = 0;
  v3 = ZwOpenKey(&KeyHandle, 0x20000u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    v3 = ZwOpenKey(&Handle, 0x40000u, &v8);
    if ( v3 >= 0 )
    {
      v3 = EnforceKeyProtection(Handle, KeyHandle);
      if ( v3 >= 0
        || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
        goto LABEL_16;
      }
      v4 = 182;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_16;
      v4 = 181;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_16;
    v4 = 180;
  }
  _mm_lfence();
  WPP_SF_qD(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
    KeGetCurrentThread(),
    v3);
LABEL_16:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14007d5d4  mov     [rsp-8+arg_8], rbx
0x14007d5d9  push    rbp
0x14007d5da  lea     rbp, [rsp-57h]
0x14007d5df  sub     rsp, 0C0h
0x14007d5e6  mov     rax, cs:__security_cookie
0x14007d5ed  xor     rax, rsp
0x14007d5f0  mov     [rbp+57h+var_10], rax
0x14007d5f4  mov     rbx, rcx
0x14007d5f7  mov     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x14007d5fe  xorps   xmm0, xmm0
0x14007d601  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x14007d608  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007d60c  mov     [rbp+57h+KeyHandle], 0
0x14007d614  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x14007d61b  mov     dword ptr [rbp+57h+var_50+4], 0
0x14007d622  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14007d626  mov     dword ptr [rbp+57h+var_50+1Ch], 0
0x14007d62d  mov     [rbp+57h+Handle], 0
0x14007d635  call    cs:__imp_RtlInitUnicodeString
0x14007d63c  nop     dword ptr [rax+rax+00h]
0x14007d641  test    rbx, rbx
0x14007d644  jnz     short loc_14007D650
0x14007d646  mov     eax, 0C000000Dh
0x14007d64b  jmp     loc_14007D79D
0x14007d650  mov     edx, 30h ; '0'
0x14007d655  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14007d65d  mov     ecx, 240h
0x14007d662  mov     [rbp+57h+ObjectAttributes.Length], edx
0x14007d665  xorps   xmm0, xmm0
0x14007d668  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x14007d66b  mov     [rbp+57h+var_50.Length], edx
0x14007d66e  lea     rax, [rbp+57h+DestinationString]
0x14007d672  mov     [rbp+57h+var_50.Attributes], ecx
0x14007d675  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14007d679  mov     edx, 20000h; DesiredAccess
0x14007d67e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14007d682  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14007d686  mov     [rbp+57h+var_50.RootDirectory], 0
0x14007d68e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007d693  mov     [rbp+57h+var_50.ObjectName], rbx
0x14007d697  movdqu  xmmword ptr [rbp+57h+var_50.SecurityDescriptor], xmm0
0x14007d69c  call    cs:__imp_ZwOpenKey
0x14007d6a3  nop     dword ptr [rax+rax+00h]
0x14007d6a8  mov     ebx, eax
0x14007d6aa  test    eax, eax
0x14007d6ac  jns     short loc_14007D6D8
0x14007d6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d6b5  lea     rax, WPP_GLOBAL_Control
0x14007d6bc  cmp     rcx, rax
0x14007d6bf  jz      loc_14007D771
0x14007d6c5  mov     ecx, [rcx+2Ch]
0x14007d6c8  test    cl, 1
0x14007d6cb  jz      loc_14007D771
0x14007d6d1  mov     edx, 0B4h
0x14007d6d6  jmp     short loc_14007D74A
0x14007d6d8  lea     r8, [rbp+57h+var_50]; ObjectAttributes
0x14007d6dc  mov     edx, 40000h; DesiredAccess
0x14007d6e1  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x14007d6e5  call    cs:__imp_ZwOpenKey
0x14007d6ec  nop     dword ptr [rax+rax+00h]
0x14007d6f1  mov     ebx, eax
0x14007d6f3  test    eax, eax
0x14007d6f5  jns     short loc_14007D718
0x14007d6f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d6fe  lea     rax, WPP_GLOBAL_Control
0x14007d705  cmp     rcx, rax
0x14007d708  jz      short loc_14007D771
0x14007d70a  mov     eax, [rcx+2Ch]
0x14007d70d  test    al, 1
0x14007d70f  jz      short loc_14007D771
0x14007d711  mov     edx, 0B5h
0x14007d716  jmp     short loc_14007D74A
0x14007d718  mov     rdx, [rbp+57h+KeyHandle]; HANDLE
0x14007d71c  mov     rcx, [rbp+57h+Handle]; Handle
0x14007d720  call    EnforceKeyProtection
0x14007d725  mov     ebx, eax
0x14007d727  test    eax, eax
0x14007d729  jns     short loc_14007D771
0x14007d72b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d732  lea     rax, WPP_GLOBAL_Control
0x14007d739  cmp     rcx, rax
0x14007d73c  jz      short loc_14007D771
0x14007d73e  mov     eax, [rcx+2Ch]
0x14007d741  test    al, 1
0x14007d743  jz      short loc_14007D771
0x14007d745  mov     edx, 0B6h
0x14007d74a  lfence
0x14007d74d  mov     r9, gs:188h
0x14007d756  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007d75d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d764  mov     [rsp+0C0h+var_A0], ebx
0x14007d768  mov     rcx, [rcx+18h]
0x14007d76c  call    WPP_SF_qD
0x14007d771  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14007d775  test    rcx, rcx
0x14007d778  jz      short loc_14007D786
0x14007d77a  call    cs:__imp_ZwClose
0x14007d781  nop     dword ptr [rax+rax+00h]
0x14007d786  mov     rcx, [rbp+57h+Handle]; Handle
0x14007d78a  test    rcx, rcx
0x14007d78d  jz      short loc_14007D79B
0x14007d78f  call    cs:__imp_ZwClose
0x14007d796  nop     dword ptr [rax+rax+00h]
0x14007d79b  mov     eax, ebx
0x14007d79d  mov     rcx, [rbp+57h+var_10]
0x14007d7a1  xor     rcx, rsp; StackCookie
0x14007d7a4  call    __security_check_cookie
0x14007d7a9  mov     rbx, [rsp+0C0h+arg_8]
0x14007d7b1  add     rsp, 0C0h
0x14007d7b8  pop     rbp
0x14007d7b9  retn
```
