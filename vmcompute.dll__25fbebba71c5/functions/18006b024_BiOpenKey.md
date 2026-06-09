# BiOpenKey

- ea: `0x18006b024`
- end: `0x18006b248`
- name: `BiOpenKey`
- size: `548`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063b04`
- `0x180063dcc`
- `0x180064a8c`
- `0x1800650c8`
- `0x1800657b8`
- `0x180065c14`
- `0x180065f20`
- `0x18006a01c`
- `0x18006a138`
- `0x18006a970`
- `0x18006b378`
- `0x18006c374`
- `0x18006cfc8`

## callees

- `0x180069d14`
- `0x18006a2d4`
- `0x18006b024`
- `0x18006b6fc`
- `0x18006fbc0`
- `0x1800724f0`

## import_xrefs

- `ntdll!ZwClose` at `0x18006b180`
- `ntdll!ZwClose` at `0x18006b1c3`
- `ntdll!ZwClose` at `0x18006b180`
- `ntdll!ZwClose` at `0x18006b1c3`
- `ntdll!ZwSetSecurityObject` at `0x18006b13d`
- `ntdll!ZwSetSecurityObject` at `0x18006b13d`
- `ntdll!RtlFreeHeap` at `0x18006b1e6`
- `ntdll!RtlFreeHeap` at `0x18006b1e6`
- `ntdll!RtlInitUnicodeString` at `0x18006b083`
- `ntdll!RtlInitUnicodeString` at `0x18006b083`

## pseudocode

```c
__int64 __fastcall BiOpenKey(unsigned __int64 a1, const WCHAR *a2, int a3, HANDLE *a4)
{
  unsigned int i; // esi
  struct _ACL *KeySecurityDescriptor; // rdi
  int v10; // ebx
  unsigned int v11; // eax
  NTSTATUS v12; // eax
  HANDLE Handle; // [rsp+28h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+30h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-80h] BYREF
  __int128 v17; // [rsp+48h] [rbp-70h]
  _BYTE v18[96]; // [rsp+58h] [rbp-60h] BYREF
  unsigned __int64 v19; // [rsp+C0h] [rbp+8h]

  KeyHandle = 0;
  DestinationString = 0;
  v17 = 0;
  memset(v18, 0, 28);
  for ( i = 0; ; ++i )
  {
    Handle = 0;
    KeySecurityDescriptor = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    v19 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
    a3 |= 0x40000u;
    LODWORD(v17) = 48;
    *((_QWORD *)&v17 + 1) = a1 & 0xFFFFFFFFFFFFFFFDuLL;
    *(_DWORD *)&v18[8] = 64;
    *(_QWORD *)v18 = &DestinationString;
    *(_OWORD *)&v18[16] = 0;
    v10 = BiZwOpenKey(&Handle);
    if ( v10 >= 0 )
    {
      if ( (a3 & 0x60019) == a3 )
        goto LABEL_13;
      KeySecurityDescriptor = BiCreateKeySecurityDescriptor(0xF003Fu);
      if ( ((unsigned __int8)Handle & 1) != 0 )
      {
        v11 = ORSetKeySecurity((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL, 4u, KeySecurityDescriptor);
        v12 = BiDosErrorToNtStatus(v11);
      }
      else
      {
        v12 = ZwSetSecurityObject(Handle, 4u, KeySecurityDescriptor);
      }
      v10 = v12;
      if ( v12 >= 0 )
      {
        v10 = BiZwOpenKey(&KeyHandle);
        if ( v10 >= 0 )
        {
          if ( ((unsigned __int8)Handle & 1) != 0 )
            ORCloseKey((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL);
          else
            ZwClose(Handle);
          Handle = KeyHandle;
LABEL_13:
          *a4 = Handle;
        }
      }
    }
    if ( v10 < 0 && Handle )
    {
      if ( ((unsigned __int8)Handle & 1) != 0 )
        ORCloseKey((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL);
      else
        ZwClose(Handle);
    }
    if ( KeySecurityDescriptor )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, KeySecurityDescriptor);
    if ( v10 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
    a1 = v19;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006b024  mov     [rsp+arg_18], r9
0x18006b029  mov     [rsp+arg_8], rdx
0x18006b02e  push    rbx
0x18006b02f  push    rsi
0x18006b030  push    rdi
0x18006b031  push    r12
0x18006b033  push    r13
0x18006b035  push    r14
0x18006b037  push    r15
0x18006b039  sub     rsp, 80h
0x18006b040  mov     r12, r9
0x18006b043  mov     r14d, r8d
0x18006b046  mov     r13, rdx
0x18006b049  mov     rbx, rcx
0x18006b04c  mov     [rsp+0B8h+KeyHandle], 0
0x18006b055  xorps   xmm0, xmm0
0x18006b058  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x18006b05d  xor     eax, eax
0x18006b05f  movups  [rsp+0B8h+var_70], xmm0
0x18006b064  movups  [rsp+0B8h+var_60], xmm0
0x18006b069  movups  [rsp+0B8h+var_60+0Ch], xmm0
0x18006b06e  xor     esi, esi
0x18006b070  mov     [rsp+0B8h+Handle], 0
0x18006b079  xor     edi, edi
0x18006b07b  mov     rdx, r13; SourceString
0x18006b07e  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x18006b083  call    cs:__imp_RtlInitUnicodeString
0x18006b08a  nop     dword ptr [rax+rax+00h]
0x18006b08f  and     rbx, 0FFFFFFFFFFFFFFFDh
0x18006b093  mov     [rsp+0B8h+arg_0], rbx
0x18006b09b  bts     r14d, 12h
0x18006b0a0  mov     [rsp+0B8h+arg_10], r14d
0x18006b0a8  mov     r15d, r14d
0x18006b0ab  and     r15d, 60019h
0x18006b0b2  mov     dword ptr [rsp+0B8h+var_70], 30h ; '0'
0x18006b0ba  mov     qword ptr [rsp+0B8h+var_70+8], rbx
0x18006b0bf  mov     dword ptr [rsp+0B8h+var_60+8], 40h ; '@'
0x18006b0c7  lea     rax, [rsp+0B8h+DestinationString]
0x18006b0cc  mov     qword ptr [rsp+0B8h+var_60], rax
0x18006b0d1  xorps   xmm0, xmm0
0x18006b0d4  movdqu  [rsp+0B8h+var_50], xmm0
0x18006b0da  mov     edx, 40000h
0x18006b0df  cmp     r15d, r14d
0x18006b0e2  cmovz   edx, r14d
0x18006b0e6  lea     r8, [rsp+0B8h+var_70]
0x18006b0eb  lea     rcx, [rsp+0B8h+Handle]; KeyHandle
0x18006b0f0  call    BiZwOpenKey
0x18006b0f5  mov     ebx, eax
0x18006b0f7  mov     [rsp+0B8h+var_98], eax
0x18006b0fb  test    eax, eax
0x18006b0fd  js      loc_18006B19F
0x18006b103  cmp     r15d, r14d
0x18006b106  jz      loc_18006B196
0x18006b10c  mov     ecx, 0F003Fh; AccessMask
0x18006b111  call    BiCreateKeySecurityDescriptor
0x18006b116  mov     rdi, rax
0x18006b119  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18006b11e  mov     r8, rax; SecurityDescriptor
0x18006b121  mov     edx, 4; SecurityInformation
0x18006b126  test    cl, 1
0x18006b129  jz      short loc_18006B13D
0x18006b12b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18006b12f  call    ORSetKeySecurity
0x18006b134  mov     ecx, eax
0x18006b136  call    BiDosErrorToNtStatus
0x18006b13b  jmp     short loc_18006B149
0x18006b13d  call    cs:__imp_ZwSetSecurityObject
0x18006b144  nop     dword ptr [rax+rax+00h]
0x18006b149  mov     ebx, eax
0x18006b14b  test    eax, eax
0x18006b14d  js      short loc_18006B1BD
0x18006b14f  lea     r8, [rsp+0B8h+var_70]
0x18006b154  mov     edx, r14d
0x18006b157  lea     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x18006b15c  call    BiZwOpenKey
0x18006b161  mov     ebx, eax
0x18006b163  mov     [rsp+0B8h+var_98], eax
0x18006b167  test    eax, eax
0x18006b169  js      short loc_18006B19F
0x18006b16b  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18006b170  test    cl, 1
0x18006b173  jz      short loc_18006B180
0x18006b175  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18006b179  call    ORCloseKey
0x18006b17e  jmp     short loc_18006B18C
0x18006b180  call    cs:__imp_ZwClose
0x18006b187  nop     dword ptr [rax+rax+00h]
0x18006b18c  mov     rax, [rsp+0B8h+KeyHandle]
0x18006b191  mov     [rsp+0B8h+Handle], rax
0x18006b196  mov     rax, [rsp+0B8h+Handle]
0x18006b19b  mov     [r12], rax
0x18006b19f  test    ebx, ebx
0x18006b1a1  jns     short loc_18006B1CF
0x18006b1a3  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18006b1a8  test    rcx, rcx
0x18006b1ab  jz      short loc_18006B1CF
0x18006b1ad  test    cl, 1
0x18006b1b0  jz      short loc_18006B1C3
0x18006b1b2  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18006b1b6  call    ORCloseKey
0x18006b1bb  jmp     short loc_18006B1CF
0x18006b1bd  mov     [rsp+0B8h+var_98], ebx
0x18006b1c1  jmp     short loc_18006B19F
0x18006b1c3  call    cs:__imp_ZwClose
0x18006b1ca  nop     dword ptr [rax+rax+00h]
0x18006b1cf  test    rdi, rdi
0x18006b1d2  jz      short loc_18006B1F2
0x18006b1d4  mov     rcx, gs:60h
0x18006b1dd  mov     r8, rdi; P
0x18006b1e0  xor     edx, edx; Flags
0x18006b1e2  mov     rcx, [rcx+30h]; HeapHandle
0x18006b1e6  call    cs:__imp_RtlFreeHeap
0x18006b1ed  nop     dword ptr [rax+rax+00h]
0x18006b1f2  cmp     ebx, 0C000017Dh
0x18006b1f8  jnz     short loc_18006B232
0x18006b1fa  int     3; Trap to Debugger
0x18006b1fb  jmp     short loc_18006B21E
0x18006b1fd  mov     esi, 5
0x18006b202  mov     r12, [rsp+0B8h+arg_18]
0x18006b20a  mov     r14d, [rsp+0B8h+arg_10]
0x18006b212  mov     r13, [rsp+0B8h+arg_8]
0x18006b21a  mov     ebx, [rsp+0B8h+var_98]
0x18006b21e  cmp     esi, 5
0x18006b221  jnb     short loc_18006B232
0x18006b223  inc     esi
0x18006b225  mov     rbx, [rsp+0B8h+arg_0]
0x18006b22d  jmp     loc_18006B070
0x18006b232  mov     eax, ebx
0x18006b234  add     rsp, 80h
0x18006b23b  pop     r15
0x18006b23d  pop     r14
0x18006b23f  pop     r13
0x18006b241  pop     r12
0x18006b243  pop     rdi
0x18006b244  pop     rsi
0x18006b245  pop     rbx
0x18006b246  retn
```
