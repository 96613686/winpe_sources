# AslRegistryGetKey

- ea: `0x140010568`
- end: `0x14001066f`
- name: `AslRegistryGetKey`
- size: `263`
- prototype: `__int64 __fastcall(void **, const WCHAR *, ACCESS_MASK)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000c0ac`
- `0x14001687c`
- `0x140016c98`
- `0x140017498`

## callees

- `0x14001008c`
- `0x140010480`
- `0x140010568`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140010652`
- `ntdll!RtlFreeHeap` at `0x140010652`
- `ntdll!ZwOpenKey` at `0x14001060b`
- `ntdll!ZwOpenKey` at `0x14001060b`

## string_xrefs

- `0x1400105b1`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x1400105c3`: `AslRegistryGetKey`
- `0x14001061e`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  PVOID P[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v6 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "AslRegistryBuildMachinePath failed %x for %ws";
    v9 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v9, v8, v6, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v7 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v6 != -1073741772 )
  {
    v8 = "NtOpenKey failed %x for %ws";
    v9 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v7;
}

```

## disassembly

```asm
0x140010568  mov     [rsp-18h+arg_8], rbx
0x14001056d  mov     [rsp-18h+arg_10], rsi
0x140010572  push    rbp
0x140010573  push    rdi
0x140010574  push    r14
0x140010576  mov     rbp, rsp
0x140010579  sub     rsp, 70h
0x14001057d  xorps   xmm0, xmm0
0x140010580  xor     eax, eax
0x140010582  mov     [rcx], rax
0x140010585  mov     rsi, rcx
0x140010588  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001058c  lea     rcx, [rbp+P]; Destination
0x140010590  mov     [rbp+KeyHandle], rax
0x140010594  mov     r14d, r8d
0x140010597  mov     rdi, rdx
0x14001059a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001059e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400105a2  movups  xmmword ptr [rbp+P], xmm0
0x1400105a6  call    AslRegistryBuildMachinePath
0x1400105ab  mov     ebx, eax
0x1400105ad  test    eax, eax
0x1400105af  jns     short loc_1400105DA
0x1400105b1  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x1400105b8  mov     r8d, 6B6h
0x1400105be  mov     [rsp+70h+var_48], rdi
0x1400105c3  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x1400105ca  mov     ecx, 1
0x1400105cf  mov     [rsp+70h+var_50], eax
0x1400105d3  call    AslLogCallPrintf
0x1400105d8  jmp     short loc_14001063A
0x1400105da  lea     rax, [rbp+P]
0x1400105de  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400105e5  xorps   xmm0, xmm0
0x1400105e8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400105ec  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400105f0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400105f8  mov     edx, r14d; DesiredAccess
0x1400105fb  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140010602  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140010606  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001060b  call    cs:__imp_ZwOpenKey
0x140010611  mov     ebx, eax
0x140010613  test    eax, eax
0x140010615  jns     short loc_14001062D
0x140010617  cmp     eax, 0C0000034h
0x14001061c  jz      short loc_14001063A
0x14001061e  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x140010625  mov     r8d, 6E1h
0x14001062b  jmp     short loc_1400105BE
0x14001062d  mov     rax, [rbp+KeyHandle]
0x140010631  xor     ebx, ebx
0x140010633  mov     [rsi], rax
0x140010636  mov     [rbp+KeyHandle], rbx
0x14001063a  mov     r8, [rbp+P+8]; P
0x14001063e  test    r8, r8
0x140010641  jz      short loc_140010658
0x140010643  mov     rcx, gs:60h
0x14001064c  xor     edx, edx; Flags
0x14001064e  mov     rcx, [rcx+30h]; HeapHandle
0x140010652  call    cs:__imp_RtlFreeHeap
0x140010658  lea     r11, [rsp+70h+var_s0]
0x14001065d  mov     eax, ebx
0x14001065f  mov     rbx, [r11+28h]
0x140010663  mov     rsi, [r11+30h]
0x140010667  mov     rsp, r11
0x14001066a  pop     r14
0x14001066c  pop     rdi
0x14001066d  pop     rbp
0x14001066e  retn
```
