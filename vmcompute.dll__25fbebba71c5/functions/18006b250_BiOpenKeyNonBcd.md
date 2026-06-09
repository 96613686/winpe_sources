# BiOpenKeyNonBcd

- ea: `0x18006b250`
- end: `0x18006b371`
- name: `BiOpenKeyNonBcd`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006a210`
- `0x18006abe4`

## callees

- `0x18006b250`

## import_xrefs

- `ntdll!ZwClose` at `0x18006b314`
- `ntdll!ZwClose` at `0x18006b314`
- `ntdll!ZwOpenKey` at `0x18006b2e8`
- `ntdll!ZwOpenKey` at `0x18006b2e8`
- `ntdll!RtlInitUnicodeString` at `0x18006b2a7`
- `ntdll!RtlInitUnicodeString` at `0x18006b2a7`

## pseudocode

```c
__int64 __fastcall BiOpenKeyNonBcd(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  unsigned int i; // edi
  NTSTATUS v9; // ebx
  void *KeyHandle; // [rsp+28h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  for ( i = 0; ; ++i )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
    if ( v9 < 0 )
    {
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      *a4 = KeyHandle;
    }
    if ( v9 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006b250  mov     rax, rsp
0x18006b253  mov     [rax+20h], r9
0x18006b257  mov     [rax+18h], r8d
0x18006b25b  mov     [rax+10h], rdx
0x18006b25f  mov     [rax+8], rcx
0x18006b263  push    rbx
0x18006b264  push    rsi
0x18006b265  push    rdi
0x18006b266  push    r12
0x18006b268  push    r14
0x18006b26a  push    r15
0x18006b26c  sub     rsp, 78h
0x18006b270  mov     rsi, r9
0x18006b273  mov     r14d, r8d
0x18006b276  mov     r15, rdx
0x18006b279  mov     r12, rcx
0x18006b27c  xorps   xmm0, xmm0
0x18006b27f  movups  xmmword ptr [rax-78h], xmm0
0x18006b283  xor     eax, eax
0x18006b285  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x18006b28a  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x18006b28f  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x18006b294  xor     edi, edi
0x18006b296  mov     [rsp+0A8h+KeyHandle], 0
0x18006b29f  mov     rdx, r15; SourceString
0x18006b2a2  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x18006b2a7  call    cs:__imp_RtlInitUnicodeString
0x18006b2ae  nop     dword ptr [rax+rax+00h]
0x18006b2b3  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18006b2bb  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x18006b2c0  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x18006b2c8  lea     rax, [rsp+0A8h+DestinationString]
0x18006b2cd  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x18006b2d2  xorps   xmm0, xmm0
0x18006b2d5  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b2db  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18006b2e0  mov     edx, r14d; DesiredAccess
0x18006b2e3  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x18006b2e8  call    cs:__imp_ZwOpenKey
0x18006b2ef  nop     dword ptr [rax+rax+00h]
0x18006b2f4  mov     ebx, eax
0x18006b2f6  mov     [rsp+0A8h+var_88], eax
0x18006b2fa  test    eax, eax
0x18006b2fc  js      short loc_18006B306
0x18006b2fe  mov     rcx, [rsp+0A8h+KeyHandle]
0x18006b303  mov     [rsi], rcx
0x18006b306  test    ebx, ebx
0x18006b308  jns     short loc_18006B320
0x18006b30a  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x18006b30f  test    rcx, rcx
0x18006b312  jz      short loc_18006B320
0x18006b314  call    cs:__imp_ZwClose
0x18006b31b  nop     dword ptr [rax+rax+00h]
0x18006b320  cmp     ebx, 0C000017Dh
0x18006b326  jnz     short loc_18006B360
0x18006b328  int     3; Trap to Debugger
0x18006b329  jmp     short loc_18006B354
0x18006b32b  mov     edi, 5
0x18006b330  mov     rsi, [rsp+0A8h+arg_18]
0x18006b338  mov     r14d, [rsp+0A8h+arg_10]
0x18006b340  mov     r15, [rsp+0A8h+arg_8]
0x18006b348  mov     r12, [rsp+0A8h+arg_0]
0x18006b350  mov     ebx, [rsp+0A8h+var_88]
0x18006b354  cmp     edi, 5
0x18006b357  jnb     short loc_18006B360
0x18006b359  inc     edi
0x18006b35b  jmp     loc_18006B296
0x18006b360  mov     eax, ebx
0x18006b362  add     rsp, 78h
0x18006b366  pop     r15
0x18006b368  pop     r14
0x18006b36a  pop     r12
0x18006b36c  pop     rdi
0x18006b36d  pop     rsi
0x18006b36e  pop     rbx
0x18006b36f  retn
```
