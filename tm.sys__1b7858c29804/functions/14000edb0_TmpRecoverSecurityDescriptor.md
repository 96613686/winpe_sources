# TmpRecoverSecurityDescriptor

- ea: `0x14000edb0`
- end: `0x14000eede`
- name: `TmpRecoverSecurityDescriptor`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e758`
- `0x14000ebd4`
- `0x14000eee4`

## callees

- `0x140001a0c`
- `0x14000edb0`

## import_xrefs

- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000ee35`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000ee35`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000ee69`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000ee69`

## pseudocode

```c
__int64 __fastcall TmpRecoverSecurityDescriptor(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        ULONG a4,
        PSECURITY_DESCRIPTOR *a5)
{
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx

  if ( a3 + a4 > a2 || a4 > a2 || a3 > a2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
      return 3222863920LL;
    v8 = 12;
    goto LABEL_22;
  }
  if ( a4 >= 0x28 )
  {
    v9 = (void *)(a3 + a1);
    *a5 = v9;
    if ( !RtlValidRelativeSecurityDescriptor(v9, a4, 0) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
        return 3222863920LL;
      v8 = 14;
      goto LABEL_22;
    }
    if ( RtlLengthSecurityDescriptor(*a5) == a4 )
      return 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    {
      v8 = 15;
      goto LABEL_22;
    }
  }
  else
  {
    if ( !a4 )
    {
      *a5 = 0;
      return 0;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    {
      v8 = 13;
LABEL_22:
      WPP_SF_(v7[3], v8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids);
    }
  }
  return 3222863920LL;
}

```

## disassembly

```asm
0x14000edb0  mov     [rsp+arg_0], rbx
0x14000edb5  push    rdi
0x14000edb6  sub     rsp, 20h
0x14000edba  lea     eax, [r8+r9]
0x14000edbe  mov     ebx, r9d
0x14000edc1  cmp     eax, edx
0x14000edc3  ja      loc_14000EE9E
0x14000edc9  cmp     ebx, edx
0x14000edcb  ja      loc_14000EE9E
0x14000edd1  cmp     r8d, edx
0x14000edd4  ja      loc_14000EE9E
0x14000edda  cmp     ebx, 28h ; '('
0x14000eddd  jnb     short loc_14000EE22
0x14000eddf  test    ebx, ebx
0x14000ede1  jnz     short loc_14000EDF6
0x14000ede3  mov     rax, [rsp+28h+arg_20]
0x14000ede8  mov     qword ptr [rax], 0
0x14000edef  xor     eax, eax
0x14000edf1  jmp     loc_14000EED2
0x14000edf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edfd  lea     rax, WPP_GLOBAL_Control
0x14000ee04  cmp     rcx, rax
0x14000ee07  jz      loc_14000EECD
0x14000ee0d  mov     eax, [rcx+2Ch]
0x14000ee10  test    al, 8
0x14000ee12  jz      loc_14000EECD
0x14000ee18  mov     edx, 0Dh
0x14000ee1d  jmp     loc_14000EEBD
0x14000ee22  mov     rdi, [rsp+28h+arg_20]
0x14000ee27  mov     edx, ebx; SecurityDescriptorLength
0x14000ee29  mov     eax, r8d
0x14000ee2c  xor     r8d, r8d; RequiredInformation
0x14000ee2f  add     rcx, rax; SecurityDescriptorInput
0x14000ee32  mov     [rdi], rcx
0x14000ee35  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14000ee3c  nop     dword ptr [rax+rax+00h]
0x14000ee41  test    al, al
0x14000ee43  jnz     short loc_14000EE66
0x14000ee45  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee4c  lea     rax, WPP_GLOBAL_Control
0x14000ee53  cmp     rcx, rax
0x14000ee56  jz      short loc_14000EECD
0x14000ee58  mov     eax, [rcx+2Ch]
0x14000ee5b  test    al, 8
0x14000ee5d  jz      short loc_14000EECD
0x14000ee5f  mov     edx, 0Eh
0x14000ee64  jmp     short loc_14000EEBD
0x14000ee66  mov     rcx, [rdi]; SecurityDescriptor
0x14000ee69  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000ee70  nop     dword ptr [rax+rax+00h]
0x14000ee75  cmp     eax, ebx
0x14000ee77  jz      loc_14000EDEF
0x14000ee7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee84  lea     rax, WPP_GLOBAL_Control
0x14000ee8b  cmp     rcx, rax
0x14000ee8e  jz      short loc_14000EECD
0x14000ee90  mov     eax, [rcx+2Ch]
0x14000ee93  test    al, 8
0x14000ee95  jz      short loc_14000EECD
0x14000ee97  mov     edx, 0Fh
0x14000ee9c  jmp     short loc_14000EEBD
0x14000ee9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eea5  lea     rax, WPP_GLOBAL_Control
0x14000eeac  cmp     rcx, rax
0x14000eeaf  jz      short loc_14000EECD
0x14000eeb1  mov     eax, [rcx+2Ch]
0x14000eeb4  test    al, 8
0x14000eeb6  jz      short loc_14000EECD
0x14000eeb8  mov     edx, 0Ch
0x14000eebd  mov     rcx, [rcx+18h]
0x14000eec1  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14000eec8  call    WPP_SF_
0x14000eecd  mov     eax, 0C0190030h
0x14000eed2  mov     rbx, [rsp+28h+arg_0]
0x14000eed7  add     rsp, 20h
0x14000eedb  pop     rdi
0x14000eedc  retn
```
