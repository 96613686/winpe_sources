# TpmRegistry::InitRegistryKey(_UNICODE_STRING *,ushort const *,TpmRegistry::KEY_VALUES)

- ea: `0x14000a19c`
- end: `0x14000a3c7`
- name: `?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEBGW4KEY_VALUES@1@@Z`
- size: `555`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000a164`
- `0x14002fc8c`
- `0x14003005c`
- `0x140030150`

## callees

- `0x14000a164`
- `0x14000a19c`
- `0x14000a410`
- `0x14000e030`
- `0x140022050`
- `0x140039b40`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000a21c`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000a2d4`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000a21c`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14000a2d4`
- `ntoskrnl!ExAllocatePool2` at `0x14000a252`
- `ntoskrnl!ExAllocatePool2` at `0x14000a252`
- `ntoskrnl!_wcsnicmp` at `0x14000a390`
- `ntoskrnl!_wcsnicmp` at `0x14000a390`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a314`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a314`

## pseudocode

```c
__int64 __fastcall TpmRegistry::InitRegistryKey(struct _UNICODE_STRING *a1, const wchar_t *a2, unsigned int a3)
{
  void *v3; // rdi
  char v4; // bp
  const wchar_t *v7; // r14
  int inited; // ebx
  unsigned __int64 v9; // rdx
  _QWORD *Pool2; // rax
  unsigned int v12; // ebx
  int v13; // edx
  int v14; // r8d
  unsigned int i; // ebx
  __int64 v16; // r11
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v18; // [rsp+78h] [rbp+10h] BYREF
  size_t pcbLength; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v4 = a3;
  v18 = 0;
  if ( a2 && a1 && a3 <= 0x23 )
  {
    if ( a3 == 35 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, a2);
      for ( i = 0; i < 0x23; ++i )
      {
        pcbLength = 0;
        RtlStringCbLengthW((STRSAFE_PCNZWCH)*(&TpmRegistry::m_LookupTable + 2 * i + 1), (size_t)a2, &pcbLength);
        if ( !_wcsnicmp(a2, (const wchar_t *)*(&TpmRegistry::m_LookupTable + v16 + 1), pcbLength) )
        {
          inited = TpmRegistry::InitRegistryKey(a1, i);
          goto LABEL_12;
        }
      }
      v7 = a2;
    }
    else
    {
      v7 = (const wchar_t *)*(&TpmRegistry::m_LookupTable + 2 * (int)a3);
    }
    inited = RtlGetPersistedStateLocation(v7, 0, a2, 0, 0, 0, &v18);
    if ( inited == -2147483643 )
    {
      v9 = v18 + 18LL;
      if ( v9 < (unsigned __int64)v18 + 2 )
        goto LABEL_11;
      Pool2 = (_QWORD *)ExAllocatePool2(257, v9, 1349349460);
      v3 = Pool2;
      if ( Pool2 )
      {
        *Pool2 = retaddr;
        Pool2[1] = retaddr;
        v3 = Pool2 + 2;
      }
      if ( v3 )
      {
        v12 = v18;
        memset(v3, 0, v18 + 2LL);
        inited = RtlGetPersistedStateLocation(v7, 0, a2, 0, v3, v12, &v18);
        if ( inited >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_SSd(WPP_GLOBAL_Control->AttachedDevice, v13, v14, (_DWORD)v3, (__int64)a2, v4);
          }
          RtlInitUnicodeString(a1, (PCWSTR)v3);
          v3 = 0;
        }
      }
      else
      {
LABEL_11:
        inited = -1073741670;
      }
    }
  }
  else
  {
    inited = -1073741811;
  }
LABEL_12:
  TpmFree(v3);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14000a19c  mov     [rsp+arg_0], rbx
0x14000a1a1  mov     [rsp+arg_10], rbp
0x14000a1a6  push    rsi
0x14000a1a7  push    rdi
0x14000a1a8  push    r13
0x14000a1aa  push    r14
0x14000a1ac  push    r15
0x14000a1ae  sub     rsp, 40h
0x14000a1b2  xor     edi, edi
0x14000a1b4  movsxd  rbp, r8d
0x14000a1b7  mov     [rsp+68h+arg_8], 0
0x14000a1bf  mov     rsi, rdx
0x14000a1c2  mov     r15, rcx
0x14000a1c5  test    rdx, rdx
0x14000a1c8  jz      loc_14000A3BD
0x14000a1ce  test    rcx, rcx
0x14000a1d1  jz      loc_14000A3BD
0x14000a1d7  cmp     ebp, 23h ; '#'
0x14000a1da  ja      loc_14000A3BD
0x14000a1e0  lea     r13, WPP_GLOBAL_Control
0x14000a1e7  jz      loc_14000A327
0x14000a1ed  mov     rax, rbp
0x14000a1f0  lea     r14, ?m_LookupTable@TpmRegistry@@0PAU_TPM_REGKEY_LOOKUP@1@A; TpmRegistry::_TPM_REGKEY_LOOKUP near * TpmRegistry::m_LookupTable
0x14000a1f7  add     rax, rax
0x14000a1fa  mov     r14, [r14+rax*8]
0x14000a1fe  lea     rax, [rsp+68h+arg_8]
0x14000a203  xor     r9d, r9d
0x14000a206  mov     [rsp+68h+var_38], rax
0x14000a20b  mov     r8, rsi
0x14000a20e  mov     [rsp+68h+var_40], edi
0x14000a212  xor     edx, edx
0x14000a214  mov     rcx, r14
0x14000a217  mov     [rsp+68h+var_48], rdi
0x14000a21c  call    cs:__imp_RtlGetPersistedStateLocation
0x14000a223  nop     dword ptr [rax+rax+00h]
0x14000a228  mov     ebx, eax
0x14000a22a  cmp     eax, 80000005h
0x14000a22f  jnz     short loc_14000A280
0x14000a231  mov     eax, [rsp+68h+arg_8]
0x14000a235  mov     rbx, [rsp+68h]
0x14000a23a  add     rax, 2
0x14000a23e  lea     rdx, [rax+10h]
0x14000a242  cmp     rdx, rax
0x14000a245  jb      short loc_14000A27B
0x14000a247  mov     ecx, 101h
0x14000a24c  mov     r8d, 506D7054h
0x14000a252  call    cs:__imp_ExAllocatePool2
0x14000a259  nop     dword ptr [rax+rax+00h]
0x14000a25e  mov     rdi, rax
0x14000a261  test    rax, rax
0x14000a264  jz      short loc_14000A276
0x14000a266  mov     [rax], rbx
0x14000a269  mov     rax, [rsp+68h]
0x14000a26e  mov     [rdi+8], rax
0x14000a272  add     rdi, 10h
0x14000a276  test    rdi, rdi
0x14000a279  jnz     short loc_14000A2A4
0x14000a27b  mov     ebx, 0C000009Ah
0x14000a280  mov     rcx, rdi; void *
0x14000a283  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000a288  lea     r11, [rsp+68h+var_28]
0x14000a28d  mov     eax, ebx
0x14000a28f  mov     rbx, [r11+30h]
0x14000a293  mov     rbp, [r11+40h]
0x14000a297  mov     rsp, r11
0x14000a29a  pop     r15
0x14000a29c  pop     r14
0x14000a29e  pop     r13
0x14000a2a0  pop     rdi
0x14000a2a1  pop     rsi
0x14000a2a2  retn
0x14000a2a4  mov     ebx, [rsp+68h+arg_8]
0x14000a2a8  xor     edx, edx; Val
0x14000a2aa  mov     rcx, rdi; void *
0x14000a2ad  lea     r8, [rbx+2]; Size
0x14000a2b1  call    memset
0x14000a2b6  lea     rax, [rsp+68h+arg_8]
0x14000a2bb  xor     r9d, r9d
0x14000a2be  mov     [rsp+68h+var_38], rax
0x14000a2c3  mov     r8, rsi
0x14000a2c6  mov     [rsp+68h+var_40], ebx
0x14000a2ca  xor     edx, edx
0x14000a2cc  mov     rcx, r14
0x14000a2cf  mov     [rsp+68h+var_48], rdi
0x14000a2d4  call    cs:__imp_RtlGetPersistedStateLocation
0x14000a2db  nop     dword ptr [rax+rax+00h]
0x14000a2e0  mov     ebx, eax
0x14000a2e2  test    eax, eax
0x14000a2e4  js      short loc_14000A280
0x14000a2e6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a2ed  cmp     rcx, r13
0x14000a2f0  jz      short loc_14000A30E
0x14000a2f2  mov     eax, [rcx+2Ch]
0x14000a2f5  test    al, 4
0x14000a2f7  jz      short loc_14000A30E
0x14000a2f9  mov     rcx, [rcx+18h]
0x14000a2fd  mov     r9, rdi
0x14000a300  mov     [rsp+68h+var_40], ebp
0x14000a304  mov     [rsp+68h+var_48], rsi
0x14000a309  call    WPP_SF_SSd
0x14000a30e  mov     rdx, rdi; SourceString
0x14000a311  mov     rcx, r15; DestinationString
0x14000a314  call    cs:__imp_RtlInitUnicodeString
0x14000a31b  nop     dword ptr [rax+rax+00h]
0x14000a320  xor     edi, edi
0x14000a322  jmp     loc_14000A280
0x14000a327  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a32e  cmp     rcx, r13
0x14000a331  jz      short loc_14000A352
0x14000a333  mov     eax, [rcx+2Ch]
0x14000a336  test    al, 4
0x14000a338  jz      short loc_14000A352
0x14000a33a  mov     rcx, [rcx+18h]
0x14000a33e  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14000a345  mov     edx, 0Ah
0x14000a34a  mov     r9, rsi
0x14000a34d  call    WPP_SF_S
0x14000a352  xor     ebx, ebx
0x14000a354  lea     r14, ?m_LookupTable@TpmRegistry@@0PAU_TPM_REGKEY_LOOKUP@1@A; TpmRegistry::_TPM_REGKEY_LOOKUP near * TpmRegistry::m_LookupTable
0x14000a35b  cmp     ebx, 23h ; '#'
0x14000a35e  jnb     short loc_14000A3B5
0x14000a360  mov     r11d, ebx
0x14000a363  lea     r8, [rsp+68h+pcbLength]; pcbLength
0x14000a36b  add     r11, r11
0x14000a36e  mov     [rsp+68h+pcbLength], rdi
0x14000a376  mov     rcx, [r14+r11*8+8]; psz
0x14000a37b  call    RtlStringCbLengthW
0x14000a380  mov     rdx, [r14+r11*8+8]; Str2
0x14000a385  mov     rcx, rsi; Str1
0x14000a388  mov     r8, [rsp+68h+pcbLength]; MaxCount
0x14000a390  call    cs:__imp__wcsnicmp
0x14000a397  nop     dword ptr [rax+rax+00h]
0x14000a39c  test    eax, eax
0x14000a39e  jz      short loc_14000A3A4
0x14000a3a0  inc     ebx
0x14000a3a2  jmp     short loc_14000A35B
0x14000a3a4  mov     edx, ebx
0x14000a3a6  mov     rcx, r15
0x14000a3a9  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)
0x14000a3ae  mov     ebx, eax
0x14000a3b0  jmp     loc_14000A280
0x14000a3b5  mov     r14, rsi
0x14000a3b8  jmp     loc_14000A1FE
0x14000a3bd  mov     ebx, 0C000000Dh
0x14000a3c2  jmp     loc_14000A280
```
