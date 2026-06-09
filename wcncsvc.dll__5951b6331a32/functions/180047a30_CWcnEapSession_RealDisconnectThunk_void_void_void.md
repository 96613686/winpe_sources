# CWcnEapSession::RealDisconnectThunk(void *,void *,void *)

- ea: `0x180047a30`
- end: `0x180047b85`
- name: `?RealDisconnectThunk@CWcnEapSession@@CAXPEAX00@Z`
- size: `341`
- prototype: `void __fastcall(void *, void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004f2c`
- `0x180015db4`
- `0x180047a30`
- `0x1800504cc`
- `0x180056de6`
- `0x180056dfe`

## import_xrefs

- `wlanapi!WlanQueryInterface` at `0x180047a83`
- `wlanapi!WlanQueryInterface` at `0x180047a83`
- `wlanapi!WlanDisconnect` at `0x180047af3`
- `wlanapi!WlanDisconnect` at `0x180047af3`
- `wlanapi!WlanFreeMemory` at `0x180047b55`
- `wlanapi!WlanFreeMemory` at `0x180047b55`

## string_xrefs

- `0x180047ab2`: `WCN Temporary Profile`

## pseudocode

```c
void __fastcall CWcnEapSession::RealDisconnectThunk(void *a1, char *a2, void *a3)
{
  void *v3; // rcx
  _DWORD *v5; // rbx
  unsigned int v6; // eax
  signed int v7; // eax
  unsigned int v8; // ecx
  CWcnSession *v9; // rcx
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF
  PVOID pMemory; // [rsp+68h] [rbp+20h] BYREF

  v3 = (void *)*((_QWORD *)a2 + 7);
  pMemory = 0;
  if ( !v3 )
    return;
  v10 = 0;
  if ( WlanQueryInterface(v3, (const GUID *)a2 + 4, wlan_intf_opcode_current_connection, 0, &v10, &pMemory, 0) )
    goto LABEL_14;
  *((_WORD *)pMemory + 259) = 0;
  v5 = pMemory;
  if ( *((_DWORD *)pMemory + 1) == 1 && !wcscmp_0((const wchar_t *)pMemory + 4, L"WCN Temporary Profile") )
  {
    v6 = *((_DWORD *)a2 + 20);
    if ( v5[130] == v6 && !memcmp_0(v5 + 131, a2 + 84, v6) )
    {
      v7 = WlanDisconnect(*((HANDLE *)a2 + 7), (const GUID *)a2 + 4, 0);
      if ( v7 )
      {
        v8 = v7 > 0 ? (unsigned __int16)v7 | 0x80070000 : v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids,
            (unsigned int)v7,
            v8 | 0x80000000);
      }
LABEL_14:
      v5 = pMemory;
    }
  }
  if ( v5 )
    WlanFreeMemory(v5);
  WcnWlanCloseHandle(*((HANDLE *)a2 + 7));
  v9 = (CWcnSession *)*((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 7) = 0;
  CWcnSession::FinishDisconnect(v9);
}

```

## disassembly

```asm
0x180047a30  mov     r11, rsp
0x180047a33  mov     [r11+8], rbx
0x180047a37  mov     [r11+18h], rsi
0x180047a3b  push    rdi
0x180047a3c  sub     rsp, 40h
0x180047a40  mov     rcx, [rdx+38h]; hClientHandle
0x180047a44  mov     rdi, rdx
0x180047a47  mov     qword ptr [r11+20h], 0
0x180047a4f  test    rcx, rcx
0x180047a52  jz      loc_180047B75
0x180047a58  lea     rax, [r11+20h]
0x180047a5c  mov     qword ptr [r11-18h], 0
0x180047a64  mov     [r11-20h], rax
0x180047a68  xor     r9d, r9d; pReserved
0x180047a6b  lea     rax, [r11+10h]
0x180047a6f  mov     [rsp+48h+arg_8], 0
0x180047a77  add     rdx, 40h ; '@'; pInterfaceGuid
0x180047a7b  mov     [r11-28h], rax
0x180047a7f  lea     r8d, [r9+7]; OpCode
0x180047a83  call    cs:__imp_WlanQueryInterface
0x180047a89  test    eax, eax
0x180047a8b  jnz     loc_180047B48
0x180047a91  mov     rax, [rsp+48h+pMemory]
0x180047a96  xor     ecx, ecx
0x180047a98  mov     [rax+206h], cx
0x180047a9f  mov     rbx, [rsp+48h+pMemory]
0x180047aa4  cmp     dword ptr [rbx+4], 1
0x180047aa8  jnz     loc_180047B4D
0x180047aae  lea     rcx, [rbx+8]; String1
0x180047ab2  lea     rdx, aWcnTemporaryPr; "WCN Temporary Profile"
0x180047ab9  call    wcscmp_0
0x180047abe  test    eax, eax
0x180047ac0  jnz     loc_180047B4D
0x180047ac6  mov     eax, [rdi+50h]
0x180047ac9  cmp     [rbx+208h], eax
0x180047acf  jnz     short loc_180047B4D
0x180047ad1  mov     r8d, eax; Size
0x180047ad4  lea     rdx, [rdi+54h]; Buf2
0x180047ad8  lea     rcx, [rbx+20Ch]; Buf1
0x180047adf  call    memcmp_0
0x180047ae4  test    eax, eax
0x180047ae6  jnz     short loc_180047B4D
0x180047ae8  mov     rcx, [rdi+38h]; hClientHandle
0x180047aec  lea     rdx, [rdi+40h]; pInterfaceGuid
0x180047af0  xor     r8d, r8d; pReserved
0x180047af3  call    cs:__imp_WlanDisconnect
0x180047af9  test    eax, eax
0x180047afb  jz      short loc_180047B48
0x180047afd  jg      short loc_180047B03
0x180047aff  mov     ecx, eax
0x180047b01  jmp     short loc_180047B0C
0x180047b03  movzx   ecx, ax
0x180047b06  or      ecx, 80070000h
0x180047b0c  mov     r10, cs:WPP_GLOBAL_Control
0x180047b13  lea     rdx, WPP_GLOBAL_Control
0x180047b1a  cmp     r10, rdx
0x180047b1d  jz      short loc_180047B48
0x180047b1f  cmp     byte ptr [r10+19h], 3
0x180047b24  jb      short loc_180047B48
0x180047b26  or      ecx, 80000000h
0x180047b2c  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x180047b33  mov     [rsp+48h+var_28], ecx
0x180047b37  mov     edx, 24h ; '$'
0x180047b3c  mov     rcx, [r10+10h]
0x180047b40  mov     r9d, eax
0x180047b43  call    WPP_SF_Dd
0x180047b48  mov     rbx, [rsp+48h+pMemory]
0x180047b4d  test    rbx, rbx
0x180047b50  jz      short loc_180047B5B
0x180047b52  mov     rcx, rbx; pMemory
0x180047b55  call    cs:__imp_WlanFreeMemory
0x180047b5b  mov     rcx, [rdi+38h]; hClientHandle
0x180047b5f  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x180047b64  mov     rcx, [rdi+10h]; this
0x180047b68  mov     qword ptr [rdi+38h], 0
0x180047b70  call    ?FinishDisconnect@CWcnSession@@QEAAXXZ; CWcnSession::FinishDisconnect(void)
0x180047b75  mov     rbx, [rsp+48h+arg_0]
0x180047b7a  mov     rsi, [rsp+48h+arg_10]
0x180047b7f  add     rsp, 40h
0x180047b83  pop     rdi
0x180047b84  retn
```
