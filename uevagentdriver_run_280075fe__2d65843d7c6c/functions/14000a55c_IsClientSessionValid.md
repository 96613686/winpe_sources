# IsClientSessionValid

- ea: `0x14000a55c`
- end: `0x14000a656`
- name: `IsClientSessionValid`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000a660`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a55c`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x14000a5dc`
- `ntoskrnl!ZwQueryInformationToken` at `0x14000a5dc`
- `ntoskrnl!ZwClose` at `0x14000a62c`
- `ntoskrnl!ZwClose` at `0x14000bbf0`
- `ntoskrnl!ZwClose` at `0x14000a62c`
- `ntoskrnl!ZwClose` at `0x14000bbf0`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14000a5a3`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14000a5a3`

## string_xrefs

- `0x14000a5b5`: `UevFilter.IsClientSessionValid: Failed to open process token, status = 0x%X\n`

## pseudocode

```c
unsigned __int8 IsClientSessionValid()
{
  unsigned __int8 v0; // bl
  char *v1; // rcx
  ULONG ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  DbgTrace(2, "UevFilter.IsClientSessionValid: Entry\n");
  if ( ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x80000000, 0x200u, &TokenHandle) >= 0 )
  {
    if ( ZwQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) >= 0 )
    {
      if ( ReturnLength == 4 )
      {
        if ( !TokenInformation )
        {
          v0 = 1;
          goto LABEL_11;
        }
        v1 = "UevFilter.IsClientSessionValid: Unexpected session id, id = 0x%X\n";
      }
      else
      {
        v1 = "UevFilter.IsClientSessionValid: Unexpected returned length, length = 0x%X\n";
      }
    }
    else
    {
      v1 = "UevFilter.IsClientSessionValid: Failed to get session id, status = 0x%X\n";
    }
  }
  else
  {
    v1 = "UevFilter.IsClientSessionValid: Failed to open process token, status = 0x%X\n";
  }
  DbgTraceFrmtErr(v1);
LABEL_11:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  DbgTraceFrmt(2, "UevFilter.IsClientSessionValid: Exit, retValue = 0x%X\n", v0);
  return v0;
}

```

## disassembly

```asm
0x14000a55c  push    rbx
0x14000a55e  sub     rsp, 30h
0x14000a562  xor     bl, bl
0x14000a564  mov     [rsp+38h+TokenHandle], 0
0x14000a56d  mov     [rsp+38h+TokenInformation], 0
0x14000a575  mov     [rsp+38h+arg_0], 0
0x14000a57d  lea     rdx, aUevfilterIscli_2; "UevFilter.IsClientSessionValid: Entry\n"
0x14000a584  mov     ecx, 2
0x14000a589  call    DbgTrace
0x14000a58e  nop
0x14000a58f  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x14000a594  mov     edx, 80000000h; DesiredAccess
0x14000a599  mov     r8d, 200h; HandleAttributes
0x14000a59f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000a5a3  call    cs:__imp_ZwOpenProcessTokenEx
0x14000a5aa  nop     dword ptr [rax+rax+00h]
0x14000a5af  test    eax, eax
0x14000a5b1  jns     short loc_14000A5BE
0x14000a5b3  mov     edx, eax
0x14000a5b5  lea     rcx, aUevfilterIscli; "UevFilter.IsClientSessionValid: Failed "...
0x14000a5bc  jmp     short loc_14000A61C
0x14000a5be  lea     rax, [rsp+38h+arg_0]
0x14000a5c3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14000a5c8  mov     r9d, 4; TokenInformationLength
0x14000a5ce  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14000a5d3  lea     edx, [r9+8]; TokenInformationClass
0x14000a5d7  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x14000a5dc  call    cs:__imp_ZwQueryInformationToken
0x14000a5e3  nop     dword ptr [rax+rax+00h]
0x14000a5e8  test    eax, eax
0x14000a5ea  jns     short loc_14000A5F7
0x14000a5ec  mov     edx, eax
0x14000a5ee  lea     rcx, aUevfilterIscli_3; "UevFilter.IsClientSessionValid: Failed "...
0x14000a5f5  jmp     short loc_14000A61C
0x14000a5f7  mov     edx, [rsp+38h+arg_0]
0x14000a5fb  cmp     edx, 4
0x14000a5fe  jz      short loc_14000A609
0x14000a600  lea     rcx, aUevfilterIscli_4; "UevFilter.IsClientSessionValid: Unexpec"...
0x14000a607  jmp     short loc_14000A61C
0x14000a609  mov     edx, [rsp+38h+TokenInformation]
0x14000a60d  test    edx, edx
0x14000a60f  jnz     short loc_14000A615
0x14000a611  mov     bl, 1
0x14000a613  jmp     short loc_14000A622
0x14000a615  lea     rcx, aUevfilterIscli_1; "UevFilter.IsClientSessionValid: Unexpec"...
0x14000a61c  call    DbgTraceFrmtErr
0x14000a621  nop
0x14000a622  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x14000a627  test    rcx, rcx
0x14000a62a  jz      short loc_14000A638
0x14000a62c  call    cs:__imp_ZwClose
0x14000a633  nop     dword ptr [rax+rax+00h]
0x14000a638  movzx   r8d, bl
0x14000a63c  lea     rdx, aUevfilterIscli_0; "UevFilter.IsClientSessionValid: Exit, r"...
0x14000a643  mov     ecx, 2
0x14000a648  call    DbgTraceFrmt
0x14000a64d  mov     al, bl
0x14000a64f  add     rsp, 30h
0x14000a653  pop     rbx
0x14000a654  retn
0x14000bbde  push    rbp
0x14000bbe0  sub     rsp, 30h
0x14000bbe4  mov     rbp, rdx
0x14000bbe7  mov     rcx, [rbp+50h]; Handle
0x14000bbeb  test    rcx, rcx
0x14000bbee  jz      short loc_14000BBFD
0x14000bbf0  call    cs:__imp_ZwClose
0x14000bbf7  nop     dword ptr [rax+rax+00h]
0x14000bbfc  nop
0x14000bbfd  add     rsp, 30h
0x14000bc01  pop     rbp
0x14000bc02  retn
```
