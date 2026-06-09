# PiRegStateOpenClassKey

- ea: `0x140020eb8`
- end: `0x140021043`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140021234`
- `0x1400213a0`

## callees

- `0x14000f900`
- `0x140020eb8`
- `0x14002161c`
- `0x1400216f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140020ff9`
- `ntoskrnl!ZwClose` at `0x140020ff9`
- `ntoskrnl!_snwprintf` at `0x140020f99`
- `ntoskrnl!_snwprintf` at `0x140020f99`

## string_xrefs

- `0x140020f12`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, ULONG *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  __int64 v9; // r8
  ULONG v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // esi
  int v14; // edi
  ULONG v15; // [rsp+70h] [rbp-61h] BYREF
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
      v12 = CmRegUtilCreateWstrKey((__int64)Handle, Dest, v9, v10, 0, &v15, v17);
      v13 = v15;
    }
    else
    {
      v12 = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = v12;
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
0x140020eb8  mov     [rsp-8+arg_8], rbx
0x140020ebd  push    rbp
0x140020ebe  push    rsi
0x140020ebf  push    rdi
0x140020ec0  push    r12
0x140020ec2  push    r13
0x140020ec4  push    r14
0x140020ec6  push    r15
0x140020ec8  lea     rbp, [rsp-1Fh]
0x140020ecd  sub     rsp, 0F0h
0x140020ed4  mov     rax, cs:__security_cookie
0x140020edb  xor     rax, rsp
0x140020ede  mov     [rbp+4Fh+var_40], rax
0x140020ee2  mov     r12, [rbp+4Fh+arg_20]
0x140020ee6  xor     ebx, ebx
0x140020ee8  mov     [rbp+4Fh+Handle], rbx
0x140020eec  mov     r14, r9
0x140020eef  mov     [rbp+4Fh+var_A0], rbx
0x140020ef3  mov     r13d, r8d
0x140020ef6  mov     [rbp+4Fh+var_B0], ebx
0x140020ef9  mov     r15, rcx
0x140020efc  mov     [r12], rbx
0x140020f00  test    r9, r9
0x140020f03  jz      short loc_140020F08
0x140020f05  mov     [r9], ebx
0x140020f08  lea     r9, [rbp+4Fh+Handle]
0x140020f0c  mov     r8d, 20019h
0x140020f12  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140020f19  xor     ecx, ecx
0x140020f1b  call    CmRegUtilOpenExistingWstrKey
0x140020f20  test    eax, eax
0x140020f22  js      loc_14002101B
0x140020f28  movzx   ecx, byte ptr [r15+0Eh]
0x140020f2d  movzx   edx, byte ptr [r15+0Dh]
0x140020f32  movzx   r8d, byte ptr [r15+0Ch]
0x140020f37  movzx   r9d, byte ptr [r15+0Bh]
0x140020f3c  movzx   eax, byte ptr [r15+0Fh]
0x140020f41  movzx   r10d, byte ptr [r15+0Ah]
0x140020f46  movzx   r11d, byte ptr [r15+9]
0x140020f4b  movzx   ebx, byte ptr [r15+8]
0x140020f50  movzx   edi, word ptr [r15+6]
0x140020f55  movzx   esi, word ptr [r15+4]
0x140020f5a  mov     [rsp+120h+var_B8], eax
0x140020f5e  mov     [rsp+120h+var_C0], ecx
0x140020f62  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140020f66  mov     [rsp+120h+var_C8], edx
0x140020f6a  mov     edx, 27h ; '''; Count
0x140020f6f  mov     [rsp+120h+var_D0], r8d
0x140020f74  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140020f7b  mov     [rsp+120h+var_D8], r9d
0x140020f80  mov     r9d, [r15]
0x140020f83  mov     [rsp+120h+var_E0], r10d
0x140020f88  mov     [rsp+120h+var_E8], r11d
0x140020f8d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140020f91  mov     dword ptr [rsp+120h+var_F8], edi
0x140020f95  mov     dword ptr [rsp+120h+var_100], esi
0x140020f99  call    cs:__imp__snwprintf
0x140020fa0  nop     dword ptr [rax+rax+00h]
0x140020fa5  mov     rbx, [rbp+4Fh+Handle]
0x140020fa9  lea     rdx, [rbp+4Fh+Dest]
0x140020fad  xor     eax, eax
0x140020faf  mov     rcx, rbx
0x140020fb2  mov     [rbp+4Fh+var_44], ax
0x140020fb6  test    r13d, r13d
0x140020fb9  jz      short loc_140020FE0
0x140020fbb  lea     rax, [rbp+4Fh+var_A0]
0x140020fbf  mov     [rsp+120h+var_F0], rax
0x140020fc4  lea     rax, [rbp+4Fh+var_B0]
0x140020fc8  mov     [rsp+120h+var_F8], rax
0x140020fcd  mov     [rsp+120h+var_100], 0
0x140020fd6  call    CmRegUtilCreateWstrKey
0x140020fdb  mov     esi, [rbp+4Fh+var_B0]
0x140020fde  jmp     short loc_140020FF4
0x140020fe0  lea     r9, [rbp+4Fh+var_A0]
0x140020fe4  mov     r8d, 0F003Fh
0x140020fea  call    CmRegUtilOpenExistingWstrKey
0x140020fef  mov     esi, 2
0x140020ff4  mov     rcx, rbx; Handle
0x140020ff7  mov     edi, eax
0x140020ff9  call    cs:__imp_ZwClose
0x140021000  nop     dword ptr [rax+rax+00h]
0x140021005  test    edi, edi
0x140021007  js      short loc_140021019
0x140021009  mov     rax, [rbp+4Fh+var_A0]
0x14002100d  mov     [r12], rax
0x140021011  test    r14, r14
0x140021014  jz      short loc_140021019
0x140021016  mov     [r14], esi
0x140021019  mov     eax, edi
0x14002101b  mov     rcx, [rbp+4Fh+var_40]
0x14002101f  xor     rcx, rsp; StackCookie
0x140021022  call    __security_check_cookie
0x140021027  mov     rbx, [rsp+120h+arg_8]
0x14002102f  add     rsp, 0F0h
0x140021036  pop     r15
0x140021038  pop     r14
0x14002103a  pop     r13
0x14002103c  pop     r12
0x14002103e  pop     rdi
0x14002103f  pop     rsi
0x140021040  pop     rbp
0x140021041  retn
```
