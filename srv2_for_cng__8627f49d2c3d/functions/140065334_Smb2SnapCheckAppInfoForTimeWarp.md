# Smb2SnapCheckAppInfoForTimeWarp

- ea: `0x140065334`
- end: `0x1400654e7`
- name: `Smb2SnapCheckAppInfoForTimeWarp`
- size: `435`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400644a4`
- `0x14006468c`

## callees

- `0x140038490`
- `0x140038560`
- `0x140065334`
- `0x1400654f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006543e`
- `ntoskrnl!ExAllocatePool2` at `0x14006543e`
- `ntoskrnl!ZwClose` at `0x1400654b7`
- `ntoskrnl!ZwClose` at `0x1400966f1`
- `ntoskrnl!ZwClose` at `0x1400654b7`
- `ntoskrnl!ZwClose` at `0x1400966f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400654a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400654a5`
- `ntoskrnl!NtOpenFile` at `0x1400653a3`
- `ntoskrnl!NtOpenFile` at `0x1400653a3`

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
0x140065334  mov     r11, rsp
0x140065337  mov     [r11+10h], rbx
0x14006533b  push    rdi
0x14006533c  sub     rsp, 0A0h
0x140065343  mov     rax, cs:__security_cookie
0x14006534a  xor     rax, rsp
0x14006534d  mov     [rsp+0A8h+var_10], rax
0x140065355  mov     qword ptr [r11-70h], 0
0x14006535d  xor     eax, eax
0x14006535f  mov     qword ptr [r11-68h], 30h ; '0'
0x140065367  mov     qword ptr [r11-50h], 240h
0x14006536f  mov     [r11-28h], rax
0x140065373  xorps   xmm0, xmm0
0x140065376  movups  [rsp+0A8h+var_38], xmm0
0x14006537b  mov     [r11-60h], rax
0x14006537f  mov     [r11-58h], rcx
0x140065383  movdqu  [rsp+0A8h+var_48], xmm0
0x140065389  mov     [rsp+0A8h+OpenOptions], eax; OpenOptions
0x14006538d  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x140065395  lea     r9, [r11-38h]; IoStatusBlock
0x140065399  lea     r8, [r11-68h]; ObjectAttributes
0x14006539d  xor     edx, edx; DesiredAccess
0x14006539f  lea     rcx, [r11-70h]; FileHandle
0x1400653a3  call    cs:__imp_NtOpenFile
0x1400653aa  nop     dword ptr [rax+rax+00h]
0x1400653af  test    eax, eax
0x1400653b1  js      loc_1400654C5
0x1400653b7  xorps   xmm0, xmm0
0x1400653ba  movups  [rsp+0A8h+var_20], xmm0
0x1400653c2  mov     [rsp+0A8h+var_78], 10h
0x1400653ca  lea     r9, [rsp+0A8h+var_78]
0x1400653cf  lea     r8, [rsp+0A8h+var_20]
0x1400653d7  mov     edx, 5301E0h
0x1400653dc  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1400653e1  call    Smb2SnapIssueIoctl
0x1400653e6  test    eax, eax
0x1400653e8  js      short loc_1400653FE
0x1400653ea  test    byte ptr [rsp+0A8h+var_20], 1
0x1400653f2  jz      short loc_1400653FE
0x1400653f4  mov     ebx, 0C0000010h
0x1400653f9  jmp     loc_1400654B2
0x1400653fe  lea     r9, [rsp+0A8h+var_78]
0x140065403  lea     r8, [rsp+0A8h+var_28]
0x14006540b  mov     ebx, 53019Ch
0x140065410  mov     edx, ebx
0x140065412  mov     rcx, [rsp+0A8h+Handle]; Handle
0x140065417  call    Smb2SnapIssueIoctl
0x14006541c  cmp     eax, 80000005h
0x140065421  jnz     short loc_1400653F4
0x140065423  mov     eax, dword ptr [rsp+0A8h+var_28]
0x14006542a  add     eax, 8
0x14006542d  mov     [rsp+0A8h+var_78], eax
0x140065431  mov     edx, eax
0x140065433  mov     ecx, 102h
0x140065438  mov     r8d, 6232534Ch
0x14006543e  call    cs:__imp_ExAllocatePool2
0x140065445  nop     dword ptr [rax+rax+00h]
0x14006544a  mov     rdi, rax
0x14006544d  test    rax, rax
0x140065450  jnz     short loc_140065459
0x140065452  mov     ebx, 0C000009Ah
0x140065457  jmp     short loc_1400654B2
0x140065459  lea     r9, [rsp+0A8h+var_78]
0x14006545e  mov     r8, rdi
0x140065461  mov     edx, ebx
0x140065463  mov     rcx, [rsp+0A8h+Handle]; Handle
0x140065468  call    Smb2SnapIssueIoctl
0x14006546d  mov     ebx, eax
0x14006546f  test    eax, eax
0x140065471  jns     short loc_14006547A
0x140065473  mov     ebx, 0C0000010h
0x140065478  jmp     short loc_1400654A0
0x14006547a  cmp     dword ptr [rdi], 10h
0x14006547d  jbe     short loc_1400654A0
0x14006547f  lea     rcx, [rdi+4]; Buf1
0x140065483  mov     r8d, 10h; Size
0x140065489  lea     rdx, VOLSNAP_APPINFO_GUID_CLIENT_ACCESSIBLE; Buf2
0x140065490  call    memcmp
0x140065495  neg     eax
0x140065497  sbb     ecx, ecx
0x140065499  mov     ebx, 0C0000010h
0x14006549e  and     ebx, ecx
0x1400654a0  xor     edx, edx; Tag
0x1400654a2  mov     rcx, rdi; P
0x1400654a5  call    cs:__imp_ExFreePoolWithTag
0x1400654ac  nop     dword ptr [rax+rax+00h]
0x1400654b1  nop
0x1400654b2  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1400654b7  call    cs:__imp_ZwClose
0x1400654be  nop     dword ptr [rax+rax+00h]
0x1400654c3  mov     eax, ebx
0x1400654c5  mov     rcx, [rsp+0A8h+var_10]
0x1400654cd  xor     rcx, rsp; StackCookie
0x1400654d0  call    __security_check_cookie
0x1400654d5  mov     rbx, [rsp+0A8h+arg_8]
0x1400654dd  add     rsp, 0A0h
0x1400654e4  pop     rdi
0x1400654e5  retn
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
