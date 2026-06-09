# Smb2SnapCheckAppInfoForTimeWarp

- ea: `0x140065384`
- end: `0x140065537`
- name: `Smb2SnapCheckAppInfoForTimeWarp`
- size: `435`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400644f4`
- `0x1400646dc`

## callees

- `0x140038490`
- `0x140038560`
- `0x140065384`
- `0x140065540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006548e`
- `ntoskrnl!ExAllocatePool2` at `0x14006548e`
- `ntoskrnl!ZwClose` at `0x140065507`
- `ntoskrnl!ZwClose` at `0x1400966f1`
- `ntoskrnl!ZwClose` at `0x140065507`
- `ntoskrnl!ZwClose` at `0x1400966f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400654f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400654f5`
- `ntoskrnl!NtOpenFile` at `0x1400653f3`
- `ntoskrnl!NtOpenFile` at `0x1400653f3`

## pseudocode

```c
NTSTATUS __fastcall Smb2SnapCheckAppInfoForTimeWarp(struct _UNICODE_STRING *a1)
{
  NTSTATUS result; // eax
  signed int v2; // ebx
  _DWORD *Pool2; // rdi
  HANDLE Handle; // [rsp+38h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES v5; // [rsp+40h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK v6; // [rsp+70h] [rbp-38h] BYREF
  __int64 v7; // [rsp+80h] [rbp-28h]
  __int128 v8; // [rsp+88h] [rbp-20h]

  Handle = 0;
  *(_QWORD *)&v5.Length = 48;
  *(_QWORD *)&v5.Attributes = 576;
  v7 = 0;
  v6 = 0;
  v5.RootDirectory = 0;
  v5.ObjectName = a1;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  result = NtOpenFile(&Handle, 0, &v5, &v6, 7u, 0);
  if ( result >= 0 )
  {
    v8 = 0;
    if ( (int)Smb2SnapIssueIoctl(Handle) >= 0 && (v8 & 1) != 0
      || (unsigned int)Smb2SnapIssueIoctl(Handle) != -2147483643 )
    {
      v2 = -1073741808;
    }
    else
    {
      Pool2 = (_DWORD *)ExAllocatePool2(258, (unsigned int)(v7 + 8), 1647465292);
      if ( Pool2 )
      {
        v2 = Smb2SnapIssueIoctl(Handle);
        if ( v2 >= 0 )
        {
          if ( *Pool2 > 0x10u )
            v2 = memcmp(Pool2 + 1, VOLSNAP_APPINFO_GUID_CLIENT_ACCESSIBLE, 0x10u) != 0 ? 0xC0000010 : 0;
        }
        else
        {
          v2 = -1073741808;
        }
        ExFreePoolWithTag(Pool2, 0);
      }
      else
      {
        v2 = -1073741670;
      }
    }
    ZwClose(Handle);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x140065384  mov     r11, rsp
0x140065387  mov     [r11+10h], rbx
0x14006538b  push    rdi
0x14006538c  sub     rsp, 0A0h
0x140065393  mov     rax, cs:__security_cookie
0x14006539a  xor     rax, rsp
0x14006539d  mov     [rsp+0A8h+var_10], rax
0x1400653a5  mov     qword ptr [r11-70h], 0
0x1400653ad  xor     eax, eax
0x1400653af  mov     qword ptr [r11-68h], 30h ; '0'
0x1400653b7  mov     qword ptr [r11-50h], 240h
0x1400653bf  mov     [r11-28h], rax
0x1400653c3  xorps   xmm0, xmm0
0x1400653c6  movups  [rsp+0A8h+var_38], xmm0
0x1400653cb  mov     [r11-60h], rax
0x1400653cf  mov     [r11-58h], rcx
0x1400653d3  movdqu  [rsp+0A8h+var_48], xmm0
0x1400653d9  mov     [rsp+0A8h+OpenOptions], eax; OpenOptions
0x1400653dd  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x1400653e5  lea     r9, [r11-38h]; IoStatusBlock
0x1400653e9  lea     r8, [r11-68h]; ObjectAttributes
0x1400653ed  xor     edx, edx; DesiredAccess
0x1400653ef  lea     rcx, [r11-70h]; FileHandle
0x1400653f3  call    cs:__imp_NtOpenFile
0x1400653fa  nop     dword ptr [rax+rax+00h]
0x1400653ff  test    eax, eax
0x140065401  js      loc_140065515
0x140065407  xorps   xmm0, xmm0
0x14006540a  movups  [rsp+0A8h+var_20], xmm0
0x140065412  mov     [rsp+0A8h+var_78], 10h
0x14006541a  lea     r9, [rsp+0A8h+var_78]
0x14006541f  lea     r8, [rsp+0A8h+var_20]
0x140065427  mov     edx, 5301E0h
0x14006542c  mov     rcx, [rsp+0A8h+Handle]; Handle
0x140065431  call    Smb2SnapIssueIoctl
0x140065436  test    eax, eax
0x140065438  js      short loc_14006544E
0x14006543a  test    byte ptr [rsp+0A8h+var_20], 1
0x140065442  jz      short loc_14006544E
0x140065444  mov     ebx, 0C0000010h
0x140065449  jmp     loc_140065502
0x14006544e  lea     r9, [rsp+0A8h+var_78]
0x140065453  lea     r8, [rsp+0A8h+var_28]
0x14006545b  mov     ebx, 53019Ch
0x140065460  mov     edx, ebx
0x140065462  mov     rcx, [rsp+0A8h+Handle]; Handle
0x140065467  call    Smb2SnapIssueIoctl
0x14006546c  cmp     eax, 80000005h
0x140065471  jnz     short loc_140065444
0x140065473  mov     eax, dword ptr [rsp+0A8h+var_28]
0x14006547a  add     eax, 8
0x14006547d  mov     [rsp+0A8h+var_78], eax
0x140065481  mov     edx, eax
0x140065483  mov     ecx, 102h
0x140065488  mov     r8d, 6232534Ch
0x14006548e  call    cs:__imp_ExAllocatePool2
0x140065495  nop     dword ptr [rax+rax+00h]
0x14006549a  mov     rdi, rax
0x14006549d  test    rax, rax
0x1400654a0  jnz     short loc_1400654A9
0x1400654a2  mov     ebx, 0C000009Ah
0x1400654a7  jmp     short loc_140065502
0x1400654a9  lea     r9, [rsp+0A8h+var_78]
0x1400654ae  mov     r8, rdi
0x1400654b1  mov     edx, ebx
0x1400654b3  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1400654b8  call    Smb2SnapIssueIoctl
0x1400654bd  mov     ebx, eax
0x1400654bf  test    eax, eax
0x1400654c1  jns     short loc_1400654CA
0x1400654c3  mov     ebx, 0C0000010h
0x1400654c8  jmp     short loc_1400654F0
0x1400654ca  cmp     dword ptr [rdi], 10h
0x1400654cd  jbe     short loc_1400654F0
0x1400654cf  lea     rcx, [rdi+4]; Buf1
0x1400654d3  mov     r8d, 10h; Size
0x1400654d9  lea     rdx, VOLSNAP_APPINFO_GUID_CLIENT_ACCESSIBLE; Buf2
0x1400654e0  call    memcmp
0x1400654e5  neg     eax
0x1400654e7  sbb     ecx, ecx
0x1400654e9  mov     ebx, 0C0000010h
0x1400654ee  and     ebx, ecx
0x1400654f0  xor     edx, edx; Tag
0x1400654f2  mov     rcx, rdi; P
0x1400654f5  call    cs:__imp_ExFreePoolWithTag
0x1400654fc  nop     dword ptr [rax+rax+00h]
0x140065501  nop
0x140065502  mov     rcx, [rsp+0A8h+Handle]; Handle
0x140065507  call    cs:__imp_ZwClose
0x14006550e  nop     dword ptr [rax+rax+00h]
0x140065513  mov     eax, ebx
0x140065515  mov     rcx, [rsp+0A8h+var_10]
0x14006551d  xor     rcx, rsp; StackCookie
0x140065520  call    __security_check_cookie
0x140065525  mov     rbx, [rsp+0A8h+arg_8]
0x14006552d  add     rsp, 0A0h
0x140065534  pop     rdi
0x140065535  retn
0x1400966e4  push    rbp
0x1400966e6  sub     rsp, 30h
0x1400966ea  mov     rbp, rdx
0x1400966ed  mov     rcx, [rbp+38h]; Handle
0x1400966f1  call    cs:__imp_ZwClose
0x1400966f8  nop     dword ptr [rax+rax+00h]
0x1400966fd  nop
0x1400966fe  add     rsp, 30h
0x140096702  pop     rbp
0x140096703  retn
```
