# MpQuerySessionId

- ea: `0x140056c20`
- end: `0x140056dbd`
- name: `MpQuerySessionId`
- size: `413`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002e3c4`
- `0x14003be04`
- `0x140055520`
- `0x140055eb0`
- `0x14006e7d0`
- `0x140070748`
- `0x140070e84`
- `0x1400740f0`
- `0x1400762f4`
- `0x140082380`
- `0x140084340`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140056c20`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140056c73`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140056c73`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140056c9f`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140056c9f`
- `ntoskrnl!ZwQueryInformationToken` at `0x140056d1b`
- `ntoskrnl!ZwQueryInformationToken` at `0x140056d1b`
- `ntoskrnl!ZwClose` at `0x140056cce`
- `ntoskrnl!ZwClose` at `0x140056cce`

## pseudocode

```c
__int64 __fastcall MpQuerySessionId(__int64 a1, __int64 a2, _DWORD *a3)
{
  NTSTATUS v4; // ebx
  __int64 v6; // rdx
  HANDLE Handle; // [rsp+30h] [rbp-28h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-20h] BYREF

  Handle = 0;
  ReturnLength = 0;
  if ( a3 )
    *a3 = 0;
  v4 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, 0x200u, &Handle);
  if ( v4 == -1073741700 )
  {
    v4 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &Handle);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v6 = 12;
LABEL_14:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v6,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v4);
        goto LABEL_6;
      }
      goto LABEL_6;
    }
LABEL_10:
    v4 = ZwQueryInformationToken(Handle, TokenSessionId, a3, 4u, &ReturnLength);
    if ( v4 >= 0 )
    {
      v4 = 0;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v6 = 14;
      goto LABEL_14;
    }
    goto LABEL_6;
  }
  if ( v4 >= 0 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v6 = 13;
    goto LABEL_14;
  }
LABEL_6:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140056c20  mov     [rsp+arg_0], rbx
0x140056c25  mov     [rsp+arg_8], rsi
0x140056c2a  push    rdi
0x140056c2b  sub     rsp, 50h
0x140056c2f  mov     rax, cs:__security_cookie
0x140056c36  xor     rax, rsp
0x140056c39  mov     [rsp+58h+var_18], rax
0x140056c3e  xor     esi, esi
0x140056c40  mov     rdi, r8
0x140056c43  mov     [rsp+58h+Handle], rsi
0x140056c48  mov     [rsp+58h+ReturnLength], esi
0x140056c4c  test    r8, r8
0x140056c4f  jz      short loc_140056C54
0x140056c51  mov     [r8], esi
0x140056c54  lea     rax, [rsp+58h+Handle]
0x140056c59  mov     r9d, 200h; HandleAttributes
0x140056c5f  mov     r8b, 1; OpenAsSelf
0x140056c62  mov     [rsp+58h+TokenHandle], rax; TokenHandle
0x140056c67  mov     edx, 8; DesiredAccess
0x140056c6c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140056c73  call    cs:__imp_ZwOpenThreadTokenEx
0x140056c7a  nop     dword ptr [rax+rax+00h]
0x140056c7f  mov     ebx, eax
0x140056c81  cmp     eax, 0C000007Ch
0x140056c86  jnz     short loc_140056CFA
0x140056c88  lea     r9, [rsp+58h+Handle]; TokenHandle
0x140056c8d  mov     edx, 8; DesiredAccess
0x140056c92  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140056c99  mov     r8d, 200h; HandleAttributes
0x140056c9f  call    cs:__imp_ZwOpenProcessTokenEx
0x140056ca6  nop     dword ptr [rax+rax+00h]
0x140056cab  mov     ebx, eax
0x140056cad  test    eax, eax
0x140056caf  jns     short loc_140056CFE
0x140056cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140056cb8  lea     rax, WPP_GLOBAL_Control
0x140056cbf  cmp     rcx, rax
0x140056cc2  jnz     short loc_140056D31
0x140056cc4  mov     rcx, [rsp+58h+Handle]; Handle
0x140056cc9  test    rcx, rcx
0x140056ccc  jz      short loc_140056CDA
0x140056cce  call    cs:__imp_ZwClose
0x140056cd5  nop     dword ptr [rax+rax+00h]
0x140056cda  mov     eax, ebx
0x140056cdc  mov     rcx, [rsp+58h+var_18]
0x140056ce1  xor     rcx, rsp; StackCookie
0x140056ce4  call    __security_check_cookie
0x140056ce9  mov     rbx, [rsp+58h+arg_0]
0x140056cee  mov     rsi, [rsp+58h+arg_8]
0x140056cf3  add     rsp, 50h
0x140056cf7  pop     rdi
0x140056cf8  retn
0x140056cfa  test    ebx, ebx
0x140056cfc  js      short loc_140056D70
0x140056cfe  mov     rcx, [rsp+58h+Handle]; TokenHandle
0x140056d03  lea     rax, [rsp+58h+ReturnLength]
0x140056d08  mov     r9d, 4; TokenInformationLength
0x140056d0e  mov     [rsp+58h+TokenHandle], rax; ReturnLength
0x140056d13  mov     r8, rdi; TokenInformation
0x140056d16  mov     edx, 0Ch; TokenInformationClass
0x140056d1b  call    cs:__imp_ZwQueryInformationToken
0x140056d22  nop     dword ptr [rax+rax+00h]
0x140056d27  mov     ebx, eax
0x140056d29  test    eax, eax
0x140056d2b  js      short loc_140056D99
0x140056d2d  mov     ebx, esi
0x140056d2f  jmp     short loc_140056CC4
0x140056d31  mov     eax, [rcx+2Ch]
0x140056d34  test    al, 1
0x140056d36  jz      short loc_140056CC4
0x140056d38  mov     edx, 0Ch
0x140056d3d  jmp     short loc_140056D44
0x140056d3f  mov     edx, 0Eh
0x140056d44  lfence
0x140056d47  mov     r9, gs:188h
0x140056d50  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140056d57  mov     rcx, cs:WPP_GLOBAL_Control
0x140056d5e  mov     dword ptr [rsp+58h+TokenHandle], ebx
0x140056d62  mov     rcx, [rcx+18h]
0x140056d66  call    WPP_SF_qD
0x140056d6b  jmp     loc_140056CC4
0x140056d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140056d77  lea     rax, WPP_GLOBAL_Control
0x140056d7e  cmp     rcx, rax
0x140056d81  jz      loc_140056CC4
0x140056d87  mov     eax, [rcx+2Ch]
0x140056d8a  test    al, 1
0x140056d8c  jz      loc_140056CC4
0x140056d92  mov     edx, 0Dh
0x140056d97  jmp     short loc_140056D44
0x140056d99  mov     rcx, cs:WPP_GLOBAL_Control
0x140056da0  lea     rax, WPP_GLOBAL_Control
0x140056da7  cmp     rcx, rax
0x140056daa  jz      loc_140056CC4
0x140056db0  mov     eax, [rcx+2Ch]
0x140056db3  test    al, 1
0x140056db5  jz      loc_140056CC4
0x140056dbb  jmp     short loc_140056D3F
```
