# HrGetContentURL(_GUID const &,CUString &)

- ea: `0x180018b40`
- end: `0x180018c83`
- name: `?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(UUID *Uuid, struct CUString *this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f51c`
- `0x18000f750`
- `0x180017738`
- `0x18001b960`
- `0x180049d10`

## callees

- `0x180015d90`
- `0x180018b40`
- `0x180018c8c`
- `0x180038324`
- `0x180038ce4`
- `0x180043124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018ba6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018be3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018c4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018ba6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018be3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018c4c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b5d`

## string_xrefs

- `0x180018b8a`: `udhisapi.dll?content=`

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
0x180018b40  mov     [rsp+arg_0], rbx
0x180018b45  mov     [rsp+arg_8], rbp
0x180018b4a  push    rsi
0x180018b4b  push    rdi
0x180018b4c  push    r14
0x180018b4e  sub     rsp, 30h
0x180018b52  mov     rbp, rcx
0x180018b55  mov     rsi, rdx
0x180018b58  mov     ecx, 2Ch ; ','; Size
0x180018b5d  call    cs:__imp_malloc
0x180018b63  lea     r14, WPP_GLOBAL_Control
0x180018b6a  mov     rdi, rax
0x180018b6d  test    rax, rax
0x180018b70  jz      loc_180018C3D
0x180018b76  mov     edx, 16h; cchDest
0x180018b7b  call    StringValidateDestW
0x180018b80  mov     ebx, eax
0x180018b82  test    eax, eax
0x180018b84  js      loc_180018C44
0x180018b8a  lea     r9, aUdhisapiDllCon_0; "udhisapi.dll?content="
0x180018b91  mov     rcx, rdi; pszDest
0x180018b94  call    StringCopyWorkerW
0x180018b99  mov     ebx, eax
0x180018b9b  test    eax, eax
0x180018b9d  js      loc_180018C49
0x180018ba3  mov     rcx, [rsi]; Block
0x180018ba6  call    cs:__imp_free
0x180018bac  mov     [rsi], rdi
0x180018baf  test    ebx, ebx
0x180018bb1  jnz     short loc_180018C02
0x180018bb3  lea     rdx, [rsp+48h+Block]; struct CUString *
0x180018bb8  mov     [rsp+48h+Block], 0
0x180018bc1  mov     rcx, rbp; Uuid
0x180018bc4  call    ?HrGUIDToUDNString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGUIDToUDNString(_GUID const &,CUString &)
0x180018bc9  mov     ebx, eax
0x180018bcb  test    eax, eax
0x180018bcd  js      short loc_180018BDE
0x180018bcf  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x180018bd4  mov     rcx, rsi; this
0x180018bd7  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180018bdc  mov     ebx, eax
0x180018bde  mov     rcx, [rsp+48h+Block]; Block
0x180018be3  call    cs:__imp_free
0x180018be9  test    ebx, ebx
0x180018beb  jnz     short loc_180018C54
0x180018bed  mov     rbp, [rsp+48h+arg_8]
0x180018bf2  mov     eax, ebx
0x180018bf4  mov     rbx, [rsp+48h+arg_0]
0x180018bf9  add     rsp, 30h
0x180018bfd  pop     r14
0x180018bff  pop     rdi
0x180018c00  pop     rsi
0x180018c01  retn
0x180018c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c09  cmp     rcx, r14
0x180018c0c  jz      short loc_180018C33
0x180018c0e  test    byte ptr [rcx+1Ch], 1
0x180018c12  jz      short loc_180018C33
0x180018c14  mov     rcx, [rcx+10h]
0x180018c18  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180018c1f  mov     edx, 0Ah
0x180018c24  mov     r9d, ebx
0x180018c27  call    WPP_SF_d
0x180018c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c33  test    ebx, ebx
0x180018c35  jns     loc_180018BB3
0x180018c3b  jmp     short loc_180018C5B
0x180018c3d  mov     ebx, 8007000Eh
0x180018c42  jmp     short loc_180018C02
0x180018c44  xor     eax, eax
0x180018c46  mov     [rdi], ax
0x180018c49  mov     rcx, rdi; Block
0x180018c4c  call    cs:__imp_free
0x180018c52  jmp     short loc_180018C02
0x180018c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c5b  cmp     rcx, r14
0x180018c5e  jz      short loc_180018BED
0x180018c60  test    byte ptr [rcx+1Ch], 1
0x180018c64  jz      short loc_180018BED
0x180018c66  mov     rcx, [rcx+10h]
0x180018c6a  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180018c71  mov     edx, 0Dh
0x180018c76  mov     r9d, ebx
0x180018c79  call    WPP_SF_d
0x180018c7e  jmp     loc_180018BED
```
