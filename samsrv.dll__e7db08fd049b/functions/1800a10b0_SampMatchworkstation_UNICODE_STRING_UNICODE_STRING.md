# SampMatchworkstation(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800a10b0`
- end: `0x1800a1367`
- name: `?SampMatchworkstation@@YAJPEAU_UNICODE_STRING@@0@Z`
- size: `695`
- prototype: `__int64 __fastcall(PUNICODE_STRING ComputerName2, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a3130`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x1800a10b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800a11e8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800a11e8`
- `ntdll!RtlEqualComputerName` at `0x1800a1224`
- `ntdll!RtlEqualComputerName` at `0x1800a1238`
- `ntdll!RtlEqualComputerName` at `0x1800a124a`
- `ntdll!RtlEqualComputerName` at `0x1800a1224`
- `ntdll!RtlEqualComputerName` at `0x1800a1238`
- `ntdll!RtlEqualComputerName` at `0x1800a124a`
- `ntdll!RtlFreeHeap` at `0x1800a1268`
- `ntdll!RtlFreeHeap` at `0x1800a129a`
- `ntdll!RtlFreeHeap` at `0x1800a12bb`
- `ntdll!RtlFreeHeap` at `0x1800a12dc`
- `ntdll!RtlFreeHeap` at `0x1800a1268`
- `ntdll!RtlFreeHeap` at `0x1800a129a`
- `ntdll!RtlFreeHeap` at `0x1800a12bb`
- `ntdll!RtlFreeHeap` at `0x1800a12dc`
- `ntdll!RtlAllocateHeap` at `0x1800a1189`
- `ntdll!RtlAllocateHeap` at `0x1800a1189`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1800a1154`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1800a1212`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1800a1154`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1800a1212`
- `ntdll!RtlCopyUnicodeString` at `0x1800a11d1`
- `ntdll!RtlCopyUnicodeString` at `0x1800a11d1`
- `ntdll!RtlInitUnicodeString` at `0x1800a11ff`
- `ntdll!RtlInitUnicodeString` at `0x1800a11ff`

## pseudocode

```c
__int64 __fastcall SampMatchworkstation(PUNICODE_STRING ComputerName2, PCUNICODE_STRING SourceString)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  struct _UNICODE_STRING *p_ComputerName; // rax
  struct _UNICODE_STRING *p_ComputerName1; // rax
  NTSTATUS v8; // ebx
  char v9; // r14
  wchar_t *i; // rcx
  wchar_t *v11; // rax
  NTSTATUS v12; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING ComputerName1; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING ComputerName; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DnsHostName; // [rsp+68h] [rbp-98h] BYREF
  char v19; // [rsp+80h] [rbp-80h] BYREF

  Context = 0;
  DnsHostName = 0;
  DestinationString = 0;
  ComputerName1 = 0;
  ComputerName = 0;
  if ( ComputerName2 && ComputerName2->Length && SourceString->Length )
  {
    v4 = 16;
    v5 = 16;
    p_ComputerName = &ComputerName;
    do
    {
      LOBYTE(p_ComputerName->Length) = 0;
      p_ComputerName = (struct _UNICODE_STRING *)((char *)p_ComputerName + 1);
      --v5;
    }
    while ( v5 );
    p_ComputerName1 = &ComputerName1;
    do
    {
      LOBYTE(p_ComputerName1->Length) = 0;
      p_ComputerName1 = (struct _UNICODE_STRING *)((char *)p_ComputerName1 + 1);
      --v4;
    }
    while ( v4 );
    v8 = RtlDnsHostNameToComputerName(&ComputerName, ComputerName2, 1u);
    if ( v8 < 0 )
      goto LABEL_25;
    if ( SourceString->Length < 0x200u )
    {
      DestinationString.MaximumLength = 512;
      DestinationString.Buffer = (PWSTR)&v19;
      v9 = 0;
    }
    else
    {
      DestinationString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString->Length + 2LL);
      if ( !DestinationString.Buffer )
      {
        v8 = -1073741670;
LABEL_25:
        if ( ComputerName.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ComputerName.Buffer);
        if ( ComputerName1.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ComputerName1.Buffer);
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            222,
            WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
            (unsigned int)v8,
            v8);
        return (unsigned int)v8;
      }
      v9 = 1;
      DestinationString.MaximumLength = SourceString->Length + 2;
    }
    v8 = -1073741712;
    RtlCopyUnicodeString(&DestinationString, SourceString);
    for ( i = DestinationString.Buffer; ; i = 0 )
    {
      v11 = wcstok(i, L",", &Context);
      if ( !v11 )
        break;
      RtlInitUnicodeString(&DnsHostName, v11);
      v12 = RtlDnsHostNameToComputerName(&ComputerName1, &DnsHostName, 1u);
      if ( v12 < 0 )
      {
        v8 = v12;
        break;
      }
      if ( RtlEqualComputerName(&DnsHostName, ComputerName2)
        || RtlEqualComputerName(&DnsHostName, &ComputerName)
        || RtlEqualComputerName(&ComputerName1, ComputerName2) )
      {
        v8 = 0;
        break;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ComputerName1.Buffer);
      ComputerName1.Buffer = 0;
    }
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    goto LABEL_25;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 221, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800a10b0  mov     [rsp-8+arg_10], rbx
0x1800a10b5  push    rbp
0x1800a10b6  push    rsi
0x1800a10b7  push    rdi
0x1800a10b8  push    r14
0x1800a10ba  push    r15
0x1800a10bc  lea     rbp, [rsp-190h]
0x1800a10c4  sub     rsp, 290h
0x1800a10cb  mov     rax, cs:__security_cookie
0x1800a10d2  xor     rax, rsp
0x1800a10d5  mov     [rbp+1B0h+var_30], rax
0x1800a10dc  xor     r15d, r15d
0x1800a10df  xorps   xmm0, xmm0
0x1800a10e2  mov     [rsp+2B0h+Context], r15
0x1800a10e7  xorps   xmm1, xmm1
0x1800a10ea  mov     rdi, rdx
0x1800a10ed  mov     rsi, rcx
0x1800a10f0  movups  xmmword ptr [rsp+2B0h+DnsHostName.Length], xmm0
0x1800a10f5  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm1
0x1800a10fa  movups  xmmword ptr [rsp+2B0h+ComputerName1.Length], xmm0
0x1800a10ff  movups  xmmword ptr [rsp+2B0h+ComputerName.Length], xmm1
0x1800a1104  test    rcx, rcx
0x1800a1107  jz      loc_1800A1312
0x1800a110d  cmp     [rcx], r15w
0x1800a1111  jz      loc_1800A1312
0x1800a1117  cmp     [rdx], r15w
0x1800a111b  jz      loc_1800A1312
0x1800a1121  lea     ecx, [r15+10h]
0x1800a1125  mov     edx, ecx
0x1800a1127  lea     rax, [rsp+2B0h+ComputerName]
0x1800a112c  mov     [rax], r15b
0x1800a112f  inc     rax
0x1800a1132  sub     rdx, 1
0x1800a1136  jnz     short loc_1800A112C
0x1800a1138  lea     rax, [rsp+2B0h+ComputerName1]
0x1800a113d  mov     [rax], r15b
0x1800a1140  inc     rax
0x1800a1143  sub     rcx, 1
0x1800a1147  jnz     short loc_1800A113D
0x1800a1149  mov     r8b, 1; AllocateComputerNameString
0x1800a114c  lea     rcx, [rsp+2B0h+ComputerName]; ComputerName
0x1800a1151  mov     rdx, rsi; DnsHostName
0x1800a1154  call    cs:__imp_RtlDnsHostNameToComputerName
0x1800a115a  mov     ebx, eax
0x1800a115c  test    eax, eax
0x1800a115e  js      loc_1800A12A0
0x1800a1164  mov     ecx, 200h
0x1800a1169  cmp     [rdi], cx
0x1800a116c  jb      short loc_1800A11B3
0x1800a116e  mov     rcx, gs:60h
0x1800a1177  mov     ebx, 2
0x1800a117c  movzx   r8d, word ptr [rdi]
0x1800a1180  xor     edx, edx; Flags
0x1800a1182  add     r8, rbx; Size
0x1800a1185  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1189  call    cs:__imp_RtlAllocateHeap
0x1800a118f  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x1800a1194  test    rax, rax
0x1800a1197  jnz     short loc_1800A11A3
0x1800a1199  mov     ebx, 0C000009Ah
0x1800a119e  jmp     loc_1800A12A0
0x1800a11a3  movzx   eax, word ptr [rdi]
0x1800a11a6  mov     r14b, 1
0x1800a11a9  add     ax, bx
0x1800a11ac  mov     [rsp+2B0h+DestinationString.MaximumLength], ax
0x1800a11b1  jmp     short loc_1800A11C4
0x1800a11b3  lea     rax, [rbp+1B0h+var_230]
0x1800a11b7  mov     [rsp+2B0h+DestinationString.MaximumLength], cx
0x1800a11bc  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x1800a11c1  mov     r14b, r15b
0x1800a11c4  mov     rdx, rdi; SourceString
0x1800a11c7  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x1800a11cc  mov     ebx, 0C0000070h
0x1800a11d1  call    cs:__imp_RtlCopyUnicodeString
0x1800a11d7  mov     rcx, [rsp+2B0h+DestinationString.Buffer]; String
0x1800a11dc  lea     r8, [rsp+2B0h+Context]; Context
0x1800a11e1  lea     rdx, asc_1800D320C; ","
0x1800a11e8  call    cs:__imp_wcstok
0x1800a11ee  test    rax, rax
0x1800a11f1  jz      loc_1800A1281
0x1800a11f7  mov     rdx, rax; SourceString
0x1800a11fa  lea     rcx, [rsp+2B0h+DnsHostName]; DestinationString
0x1800a11ff  call    cs:__imp_RtlInitUnicodeString
0x1800a1205  mov     r8b, 1; AllocateComputerNameString
0x1800a1208  lea     rdx, [rsp+2B0h+DnsHostName]; DnsHostName
0x1800a120d  lea     rcx, [rsp+2B0h+ComputerName1]; ComputerName
0x1800a1212  call    cs:__imp_RtlDnsHostNameToComputerName
0x1800a1218  test    eax, eax
0x1800a121a  js      short loc_1800A127F
0x1800a121c  mov     rdx, rsi; ComputerName2
0x1800a121f  lea     rcx, [rsp+2B0h+DnsHostName]; ComputerName1
0x1800a1224  call    cs:__imp_RtlEqualComputerName
0x1800a122a  test    al, al
0x1800a122c  jnz     short loc_1800A127A
0x1800a122e  lea     rdx, [rsp+2B0h+ComputerName]; ComputerName2
0x1800a1233  lea     rcx, [rsp+2B0h+DnsHostName]; ComputerName1
0x1800a1238  call    cs:__imp_RtlEqualComputerName
0x1800a123e  test    al, al
0x1800a1240  jnz     short loc_1800A127A
0x1800a1242  mov     rdx, rsi; ComputerName2
0x1800a1245  lea     rcx, [rsp+2B0h+ComputerName1]; ComputerName1
0x1800a124a  call    cs:__imp_RtlEqualComputerName
0x1800a1250  test    al, al
0x1800a1252  jnz     short loc_1800A127A
0x1800a1254  mov     rcx, gs:60h
0x1800a125d  xor     edx, edx; Flags
0x1800a125f  mov     r8, [rsp+2B0h+ComputerName1.Buffer]; P
0x1800a1264  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1268  call    cs:__imp_RtlFreeHeap
0x1800a126e  xor     ecx, ecx
0x1800a1270  mov     [rsp+2B0h+ComputerName1.Buffer], r15
0x1800a1275  jmp     loc_1800A11DC
0x1800a127a  mov     ebx, r15d
0x1800a127d  jmp     short loc_1800A1281
0x1800a127f  mov     ebx, eax
0x1800a1281  test    r14b, r14b
0x1800a1284  jz      short loc_1800A12A0
0x1800a1286  mov     rcx, gs:60h
0x1800a128f  xor     edx, edx; Flags
0x1800a1291  mov     r8, [rsp+2B0h+DestinationString.Buffer]; P
0x1800a1296  mov     rcx, [rcx+30h]; HeapHandle
0x1800a129a  call    cs:__imp_RtlFreeHeap
0x1800a12a0  cmp     [rsp+2B0h+ComputerName.Buffer], r15
0x1800a12a5  jz      short loc_1800A12C1
0x1800a12a7  mov     rcx, gs:60h
0x1800a12b0  xor     edx, edx; Flags
0x1800a12b2  mov     r8, [rsp+2B0h+ComputerName.Buffer]; P
0x1800a12b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800a12bb  call    cs:__imp_RtlFreeHeap
0x1800a12c1  cmp     [rsp+2B0h+ComputerName1.Buffer], r15
0x1800a12c6  jz      short loc_1800A12E2
0x1800a12c8  mov     rcx, gs:60h
0x1800a12d1  xor     edx, edx; Flags
0x1800a12d3  mov     r8, [rsp+2B0h+ComputerName1.Buffer]; P
0x1800a12d8  mov     rcx, [rcx+30h]; HeapHandle
0x1800a12dc  call    cs:__imp_RtlFreeHeap
0x1800a12e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a12e9  test    dword ptr [rcx+44h], 20000h
0x1800a12f0  jz      short loc_1800A130E
0x1800a12f2  mov     rcx, [rcx+38h]
0x1800a12f6  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a12fd  mov     edx, 0DEh
0x1800a1302  mov     [rsp+2B0h+var_290], ebx
0x1800a1306  mov     r9d, ebx
0x1800a1309  call    WPP_SF_Dd
0x1800a130e  mov     eax, ebx
0x1800a1310  jmp     short loc_1800A1341
0x1800a1312  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1319  test    dword ptr [rcx+44h], 20000h
0x1800a1320  jz      short loc_1800A133F
0x1800a1322  mov     rcx, [rcx+38h]
0x1800a1326  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a132d  mov     edx, 0DDh
0x1800a1332  mov     [rsp+2B0h+var_290], r15d
0x1800a1337  xor     r9d, r9d
0x1800a133a  call    WPP_SF_Dd
0x1800a133f  xor     eax, eax
0x1800a1341  mov     rcx, [rbp+1B0h+var_30]
0x1800a1348  xor     rcx, rsp; StackCookie
0x1800a134b  call    __security_check_cookie
0x1800a1350  mov     rbx, [rsp+2B0h+arg_10]
0x1800a1358  add     rsp, 290h
0x1800a135f  pop     r15
0x1800a1361  pop     r14
0x1800a1363  pop     rdi
0x1800a1364  pop     rsi
0x1800a1365  pop     rbp
0x1800a1366  retn
```
