# HrGetContentURL(_GUID const &,CUString &)

- ea: `0x18000d058`
- end: `0x18000d1b4`
- name: `?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(UUID *Uuid, struct CUString *this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bb00`
- `0x18000c940`
- `0x180010780`
- `0x1800373d8`
- `0x18004ce7c`

## callees

- `0x18000a060`
- `0x18000d058`
- `0x18000d1bc`
- `0x18003a798`
- `0x18003b1cc`
- `0x180045b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d0c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d107`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d177`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d0c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d107`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d177`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d075`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d075`

## string_xrefs

- `0x18000d0a8`: `udhisapi.dll?content=`

## pseudocode

```c
__int64 __fastcall HrGetContentURL(UUID *Uuid, void **this)
{
  const wchar_t *v4; // rcx
  wchar_t *v5; // rdi
  size_t v6; // r8
  size_t v7; // rdx
  HRESULT v8; // ebx
  size_t *v9; // r8
  STRSAFE_PCNZWCH v11; // rcx
  size_t v12; // [rsp+20h] [rbp-28h]
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  v5 = (wchar_t *)malloc(0x2Cu);
  if ( v5 )
  {
    v8 = StringValidateDestW(v4, 0x16u, v6);
    if ( v8 < 0 )
    {
      *v5 = 0;
    }
    else
    {
      v8 = StringCopyWorkerW(v5, v7, v9, L"udhisapi.dll?content=", v12);
      if ( v8 >= 0 )
      {
        free(*this);
        *this = v5;
        if ( !v8 )
          goto LABEL_5;
        goto LABEL_9;
      }
    }
    free(v5);
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_9:
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, (unsigned int)v8);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v8 < 0 )
    goto LABEL_18;
LABEL_5:
  Block = 0;
  v8 = HrGUIDToUDNString(Uuid, (struct CUString *)&Block);
  if ( v8 >= 0 )
    v8 = CUString::HrAppend((CUString *)this, (const unsigned __int16 *)Block);
  free(Block);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
LABEL_18:
    if ( v11 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v11[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v11 + 2), 13, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d058  mov     [rsp+arg_0], rbx
0x18000d05d  mov     [rsp+arg_8], rbp
0x18000d062  push    rsi
0x18000d063  push    rdi
0x18000d064  push    r14
0x18000d066  sub     rsp, 30h
0x18000d06a  mov     rbp, rcx
0x18000d06d  mov     rsi, rdx
0x18000d070  mov     ecx, 2Ch ; ','; Size
0x18000d075  call    cs:__imp_malloc
0x18000d07c  nop     dword ptr [rax+rax+00h]
0x18000d081  lea     r14, WPP_GLOBAL_Control
0x18000d088  mov     rdi, rax
0x18000d08b  test    rax, rax
0x18000d08e  jz      loc_18000D168
0x18000d094  mov     edx, 16h; cchDest
0x18000d099  call    StringValidateDestW
0x18000d09e  mov     ebx, eax
0x18000d0a0  test    eax, eax
0x18000d0a2  js      loc_18000D16F
0x18000d0a8  lea     r9, aUdhisapiDllCon_0; "udhisapi.dll?content="
0x18000d0af  mov     rcx, rdi; pszDest
0x18000d0b2  call    StringCopyWorkerW
0x18000d0b7  mov     ebx, eax
0x18000d0b9  test    eax, eax
0x18000d0bb  js      loc_18000D174
0x18000d0c1  mov     rcx, [rsi]; Block
0x18000d0c4  call    cs:__imp_free
0x18000d0cb  nop     dword ptr [rax+rax+00h]
0x18000d0d0  mov     [rsi], rdi
0x18000d0d3  test    ebx, ebx
0x18000d0d5  jnz     short loc_18000D12D
0x18000d0d7  lea     rdx, [rsp+48h+Block]; struct CUString *
0x18000d0dc  mov     [rsp+48h+Block], 0
0x18000d0e5  mov     rcx, rbp; Uuid
0x18000d0e8  call    ?HrGUIDToUDNString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGUIDToUDNString(_GUID const &,CUString &)
0x18000d0ed  mov     ebx, eax
0x18000d0ef  test    eax, eax
0x18000d0f1  js      short loc_18000D102
0x18000d0f3  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x18000d0f8  mov     rcx, rsi; this
0x18000d0fb  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000d100  mov     ebx, eax
0x18000d102  mov     rcx, [rsp+48h+Block]; Block
0x18000d107  call    cs:__imp_free
0x18000d10e  nop     dword ptr [rax+rax+00h]
0x18000d113  test    ebx, ebx
0x18000d115  jnz     short loc_18000D185
0x18000d117  mov     rbp, [rsp+48h+arg_8]
0x18000d11c  mov     eax, ebx
0x18000d11e  mov     rbx, [rsp+48h+arg_0]
0x18000d123  add     rsp, 30h
0x18000d127  pop     r14
0x18000d129  pop     rdi
0x18000d12a  pop     rsi
0x18000d12b  retn
0x18000d12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d134  cmp     rcx, r14
0x18000d137  jz      short loc_18000D15E
0x18000d139  test    byte ptr [rcx+1Ch], 1
0x18000d13d  jz      short loc_18000D15E
0x18000d13f  mov     rcx, [rcx+10h]
0x18000d143  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x18000d14a  mov     edx, 0Ah
0x18000d14f  mov     r9d, ebx
0x18000d152  call    WPP_SF_d
0x18000d157  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d15e  test    ebx, ebx
0x18000d160  jns     loc_18000D0D7
0x18000d166  jmp     short loc_18000D18C
0x18000d168  mov     ebx, 8007000Eh
0x18000d16d  jmp     short loc_18000D12D
0x18000d16f  xor     eax, eax
0x18000d171  mov     [rdi], ax
0x18000d174  mov     rcx, rdi; Block
0x18000d177  call    cs:__imp_free
0x18000d17e  nop     dword ptr [rax+rax+00h]
0x18000d183  jmp     short loc_18000D12D
0x18000d185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d18c  cmp     rcx, r14
0x18000d18f  jz      short loc_18000D117
0x18000d191  test    byte ptr [rcx+1Ch], 1
0x18000d195  jz      short loc_18000D117
0x18000d197  mov     rcx, [rcx+10h]
0x18000d19b  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000d1a2  mov     edx, 0Dh
0x18000d1a7  mov     r9d, ebx
0x18000d1aa  call    WPP_SF_d
0x18000d1af  jmp     loc_18000D117
```
