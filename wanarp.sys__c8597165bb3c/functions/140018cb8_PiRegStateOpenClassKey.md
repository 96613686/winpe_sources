# PiRegStateOpenClassKey

- ea: `0x140018cb8`
- end: `0x140018e43`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140019034`
- `0x1400191a0`

## callees

- `0x1400050b0`
- `0x140018cb8`
- `0x1400194c8`
- `0x140019528`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140018df9`
- `ntoskrnl!ZwClose` at `0x140018df9`
- `ntoskrnl!_snwprintf` at `0x140018d99`
- `ntoskrnl!_snwprintf` at `0x140018d99`

## string_xrefs

- `0x140018d12`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, int *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  int v9; // r8d
  int v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS WstrKey; // eax
  int v13; // esi
  int v14; // edi
  int v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h] BYREF
  void *v17[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17[0] = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class",
             131097,
             &Handle);
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      WstrKey = CmRegUtilCreateWstrKey((_DWORD)Handle, (unsigned int)Dest, v9, v10, 0, (__int64)&v15, (__int64)v17);
      v13 = v15;
    }
    else
    {
      WstrKey = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = WstrKey;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17[0];
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140018cb8  mov     [rsp-8+arg_8], rbx
0x140018cbd  push    rbp
0x140018cbe  push    rsi
0x140018cbf  push    rdi
0x140018cc0  push    r12
0x140018cc2  push    r13
0x140018cc4  push    r14
0x140018cc6  push    r15
0x140018cc8  lea     rbp, [rsp-1Fh]
0x140018ccd  sub     rsp, 0F0h
0x140018cd4  mov     rax, cs:__security_cookie
0x140018cdb  xor     rax, rsp
0x140018cde  mov     [rbp+4Fh+var_40], rax
0x140018ce2  mov     r12, [rbp+4Fh+arg_20]
0x140018ce6  xor     ebx, ebx
0x140018ce8  mov     [rbp+4Fh+Handle], rbx
0x140018cec  mov     r14, r9
0x140018cef  mov     [rbp+4Fh+var_A0], rbx
0x140018cf3  mov     r13d, r8d
0x140018cf6  mov     [rbp+4Fh+var_B0], ebx
0x140018cf9  mov     r15, rcx
0x140018cfc  mov     [r12], rbx
0x140018d00  test    r9, r9
0x140018d03  jz      short loc_140018D08
0x140018d05  mov     [r9], ebx
0x140018d08  lea     r9, [rbp+4Fh+Handle]
0x140018d0c  mov     r8d, 20019h
0x140018d12  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140018d19  xor     ecx, ecx
0x140018d1b  call    CmRegUtilOpenExistingWstrKey
0x140018d20  test    eax, eax
0x140018d22  js      loc_140018E1B
0x140018d28  movzx   ecx, byte ptr [r15+0Eh]
0x140018d2d  movzx   edx, byte ptr [r15+0Dh]
0x140018d32  movzx   r8d, byte ptr [r15+0Ch]
0x140018d37  movzx   r9d, byte ptr [r15+0Bh]
0x140018d3c  movzx   eax, byte ptr [r15+0Fh]
0x140018d41  movzx   r10d, byte ptr [r15+0Ah]
0x140018d46  movzx   r11d, byte ptr [r15+9]
0x140018d4b  movzx   ebx, byte ptr [r15+8]
0x140018d50  movzx   edi, word ptr [r15+6]
0x140018d55  movzx   esi, word ptr [r15+4]
0x140018d5a  mov     [rsp+120h+var_B8], eax
0x140018d5e  mov     [rsp+120h+var_C0], ecx
0x140018d62  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140018d66  mov     [rsp+120h+var_C8], edx
0x140018d6a  mov     edx, 27h ; '''; Count
0x140018d6f  mov     [rsp+120h+var_D0], r8d
0x140018d74  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140018d7b  mov     [rsp+120h+var_D8], r9d
0x140018d80  mov     r9d, [r15]
0x140018d83  mov     [rsp+120h+var_E0], r10d
0x140018d88  mov     [rsp+120h+var_E8], r11d
0x140018d8d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140018d91  mov     dword ptr [rsp+120h+var_F8], edi
0x140018d95  mov     dword ptr [rsp+120h+var_100], esi
0x140018d99  call    cs:__imp__snwprintf
0x140018da0  nop     dword ptr [rax+rax+00h]
0x140018da5  mov     rbx, [rbp+4Fh+Handle]
0x140018da9  lea     rdx, [rbp+4Fh+Dest]
0x140018dad  xor     eax, eax
0x140018daf  mov     rcx, rbx
0x140018db2  mov     [rbp+4Fh+var_44], ax
0x140018db6  test    r13d, r13d
0x140018db9  jz      short loc_140018DE0
0x140018dbb  lea     rax, [rbp+4Fh+var_A0]
0x140018dbf  mov     [rsp+120h+var_F0], rax
0x140018dc4  lea     rax, [rbp+4Fh+var_B0]
0x140018dc8  mov     [rsp+120h+var_F8], rax
0x140018dcd  mov     [rsp+120h+var_100], 0
0x140018dd6  call    CmRegUtilCreateWstrKey
0x140018ddb  mov     esi, [rbp+4Fh+var_B0]
0x140018dde  jmp     short loc_140018DF4
0x140018de0  lea     r9, [rbp+4Fh+var_A0]
0x140018de4  mov     r8d, 0F003Fh
0x140018dea  call    CmRegUtilOpenExistingWstrKey
0x140018def  mov     esi, 2
0x140018df4  mov     rcx, rbx; Handle
0x140018df7  mov     edi, eax
0x140018df9  call    cs:__imp_ZwClose
0x140018e00  nop     dword ptr [rax+rax+00h]
0x140018e05  test    edi, edi
0x140018e07  js      short loc_140018E19
0x140018e09  mov     rax, [rbp+4Fh+var_A0]
0x140018e0d  mov     [r12], rax
0x140018e11  test    r14, r14
0x140018e14  jz      short loc_140018E19
0x140018e16  mov     [r14], esi
0x140018e19  mov     eax, edi
0x140018e1b  mov     rcx, [rbp+4Fh+var_40]
0x140018e1f  xor     rcx, rsp; StackCookie
0x140018e22  call    __security_check_cookie
0x140018e27  mov     rbx, [rsp+120h+arg_8]
0x140018e2f  add     rsp, 0F0h
0x140018e36  pop     r15
0x140018e38  pop     r14
0x140018e3a  pop     r13
0x140018e3c  pop     r12
0x140018e3e  pop     rdi
0x140018e3f  pop     rsi
0x140018e40  pop     rbp
0x140018e41  retn
```
