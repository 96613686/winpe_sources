# CliGetKeyboardHotKeysFromRegistry(void *)

- ea: `0x1800731c0`
- end: `0x180073357`
- name: `?CliGetKeyboardHotKeysFromRegistry@@YAXPEAX@Z`
- size: `407`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006d8c8`

## callees

- `0x180018d98`
- `0x18006e170`
- `0x1800731c0`
- `0x180096e00`

## import_xrefs

- `ntdll!NtClose` at `0x18007332d`
- `ntdll!NtClose` at `0x18007332d`
- `ntdll!NtEnumerateValueKey` at `0x18007331a`
- `ntdll!NtEnumerateValueKey` at `0x18007331a`
- `ntdll!NtOpenKey` at `0x180073257`
- `ntdll!NtOpenKey` at `0x180073257`
- `ntdll!RtlInitUnicodeString` at `0x18007321a`
- `ntdll!RtlInitUnicodeString` at `0x18007321a`

## pseudocode

```c
void __fastcall CliGetKeyboardHotKeysFromRegistry(void *a1)
{
  ULONG v2; // edi
  ULONG i; // edx
  unsigned int v4; // ebx
  unsigned int v5; // edx
  unsigned int v6; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-CCh] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD KeyValueInformation[5]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v13[18]; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int16 v14[264]; // [rsp+C0h] [rbp-40h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Keyboard Layout\\DirectSwitchHotKeys");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v2 = 0;
    ResultLength = 0;
    for ( i = 0;
          NtEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, KeyValueInformation, 0x34u, &ResultLength) >= 0;
          i = v2 )
    {
      if ( KeyValueInformation[4] == 16 && KeyValueInformation[1] == 4 && KeyValueInformation[3] == 4 )
      {
        v9 = 2;
        v4 = *(_DWORD *)((char *)KeyValueInformation + KeyValueInformation[2]);
        v13[8] = 0;
        v6 = 0;
        if ( GetKeyboardDllName(v14, v13, 0, &v9, &v6) )
        {
          v5 = HIWORD(v4);
          if ( HIWORD(v4) )
          {
            if ( (v4 & 0xC0000000) == 0 )
              v5 |= 0xC000u;
          }
          CliImmSetHotKeyWorker(v6, v5, (unsigned __int16)v4, (HKL)(int)v6, 2u);
        }
      }
      ++v2;
    }
    NtClose(KeyHandle);
  }
}

```

## disassembly

```asm
0x1800731c0  mov     [rsp-8+arg_8], rbx
0x1800731c5  mov     [rsp-8+arg_10], rdi
0x1800731ca  push    rbp
0x1800731cb  lea     rbp, [rsp-1E0h]
0x1800731d3  sub     rsp, 2E0h
0x1800731da  mov     rax, cs:__security_cookie
0x1800731e1  xor     rax, rsp
0x1800731e4  mov     [rbp+1E0h+var_10], rax
0x1800731eb  xorps   xmm0, xmm0
0x1800731ee  mov     [rsp+2E0h+KeyHandle], 0
0x1800731f7  mov     rbx, rcx
0x1800731fa  lea     rdx, aKeyboardLayout_1; "Keyboard Layout\\DirectSwitchHotKeys"
0x180073201  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x180073206  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18007320b  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180073210  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180073215  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x18007321a  call    cs:__imp_RtlInitUnicodeString
0x180073220  lea     rax, [rsp+2E0h+DestinationString]
0x180073225  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18007322d  xorps   xmm0, xmm0
0x180073230  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180073235  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18007323a  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rbx
0x18007323f  mov     edx, 20019h; DesiredAccess
0x180073244  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18007324c  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180073251  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180073257  call    cs:__imp_NtOpenKey
0x18007325d  test    eax, eax
0x18007325f  js      loc_180073333
0x180073265  xor     edi, edi
0x180073267  mov     [rsp+2E0h+var_2AC], 0
0x18007326f  xor     edx, edx
0x180073271  jmp     loc_1800732F9
0x180073276  cmp     [rbp+1E0h+var_248], 10h
0x18007327a  jnz     short loc_1800732F5
0x18007327c  cmp     [rbp+1E0h+var_254], 4
0x180073280  jnz     short loc_1800732F5
0x180073282  cmp     [rbp+1E0h+var_24C], 4
0x180073286  jnz     short loc_1800732F5
0x180073288  mov     eax, [rbp+1E0h+var_250]
0x18007328b  lea     r9, [rsp+2E0h+var_2A0]; unsigned int *
0x180073290  xor     r8d, r8d; unsigned __int16
0x180073293  mov     [rsp+2E0h+var_2A0], 2
0x18007329b  lea     rdx, [rbp+1E0h+var_244]; unsigned __int16 *
0x18007329f  lea     rcx, [rbp+1E0h+var_220]; unsigned __int16 *
0x1800732a3  mov     ebx, [rbp+rax+1E0h+KeyValueInformation]
0x1800732a7  xor     eax, eax
0x1800732a9  mov     [rbp+1E0h+var_234], ax
0x1800732ad  mov     [rsp+2E0h+var_2B0], eax
0x1800732b1  lea     rax, [rsp+2E0h+var_2B0]
0x1800732b6  mov     qword ptr [rsp+2E0h+Length], rax; unsigned int *
0x1800732bb  call    ?GetKeyboardDllName@@YAPEAGPEAG0GPEAI1@Z; GetKeyboardDllName(ushort *,ushort *,ushort,uint *,uint *)
0x1800732c0  test    rax, rax
0x1800732c3  jz      short loc_1800732F5
0x1800732c5  mov     edx, ebx
0x1800732c7  shr     edx, 10h
0x1800732ca  test    edx, edx
0x1800732cc  jz      short loc_1800732DC
0x1800732ce  test    ebx, 0C0000000h
0x1800732d4  jnz     short loc_1800732DC
0x1800732d6  or      edx, 0C000h; unsigned int
0x1800732dc  movsxd  rcx, [rsp+2E0h+var_2B0]; unsigned int
0x1800732e1  mov     r9, rcx; HKL
0x1800732e4  movzx   r8d, bx; unsigned int
0x1800732e8  mov     [rsp+2E0h+Length], 2; unsigned int
0x1800732f0  call    ?CliImmSetHotKeyWorker@@YAHKIIPEAUHKL__@@K@Z; CliImmSetHotKeyWorker(ulong,uint,uint,HKL__ *,ulong)
0x1800732f5  inc     edi
0x1800732f7  mov     edx, edi; Index
0x1800732f9  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800732fe  lea     rax, [rsp+2E0h+var_2AC]
0x180073303  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180073308  lea     r9, [rbp+1E0h+KeyValueInformation]; KeyValueInformation
0x18007330c  mov     r8d, 1; KeyValueInformationClass
0x180073312  mov     [rsp+2E0h+Length], 34h ; '4'; Length
0x18007331a  call    cs:__imp_NtEnumerateValueKey
0x180073320  test    eax, eax
0x180073322  jns     loc_180073276
0x180073328  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x18007332d  call    cs:__imp_NtClose
0x180073333  mov     rcx, [rbp+1E0h+var_10]
0x18007333a  xor     rcx, rsp; StackCookie
0x18007333d  call    __security_check_cookie
0x180073342  lea     r11, [rsp+2E0h+var_s0]
0x18007334a  mov     rbx, [r11+18h]
0x18007334e  mov     rdi, [r11+20h]
0x180073352  mov     rsp, r11
0x180073355  pop     rbp
0x180073356  retn
```
