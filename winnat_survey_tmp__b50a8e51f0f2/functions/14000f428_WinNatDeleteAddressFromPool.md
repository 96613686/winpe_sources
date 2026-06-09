# WinNatDeleteAddressFromPool

- ea: `0x14000f428`
- end: `0x14000f5c3`
- name: `WinNatDeleteAddressFromPool`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000b770`

## callees

- `0x14000caa0`
- `0x14000e680`
- `0x14000e8c4`
- `0x14000f428`
- `0x14000f5cc`
- `0x14000f8fc`
- `0x1400105b0`
- `0x1400195fc`
- `0x14001ede0`
- `0x14001f440`

## pseudocode

```c
void __fastcall WinNatDeleteAddressFromPool(__int64 a1, __int64 a2, int a3)
{
  PVOID *v3; // rdi
  char v5; // bp
  PVOID v6; // rbx
  const wchar_t *v7; // r8
  size_t v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 AddressPoolEntry; // rbx
  char v15; // al
  int v16; // r9d
  char v17[16]; // [rsp+50h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-248h] BYREF
  PVOID v19; // [rsp+270h] [rbp-38h]
  int v20; // [rsp+278h] [rbp-30h]
  __int16 v21; // [rsp+27Ch] [rbp-2Ch]
  __int16 v22; // [rsp+27Eh] [rbp-2Ah]

  v3 = (PVOID *)qword_140026B08;
  v5 = 0;
  while ( v3 != &qword_140026B08 )
  {
    v6 = *(PVOID *)a1;
    if ( v3[2] == *(PVOID *)a1 )
    {
      v17[0] = 0;
      memset(pszDest, 0, sizeof(pszDest));
      v7 = (const wchar_t *)v3[4];
      v20 = *(_DWORD *)(a1 + 8);
      v22 = *((_WORD *)v3 + 13);
      v21 = *((_WORD *)v3 + 12);
      v19 = v6;
      v9 = StringCchCopyW(pszDest, v8, v7 + 172);
      v5 = v9;
      if ( v9 < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10);
      AddressPoolEntry = WinNatFindAddressPoolEntry(pszDest, v17);
      if ( AddressPoolEntry )
      {
        if ( v17[0] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12);
        v15 = *(_BYTE *)(AddressPoolEntry + 72);
        if ( (v15 & 2) != 0 )
        {
          WinNatDeleteAddressPoolEntry((PVOID)AddressPoolEntry);
        }
        else
        {
          v16 = *(unsigned __int16 *)(AddressPoolEntry + 56);
          *(_BYTE *)(AddressPoolEntry + 72) = v15 | 1;
          WinNatLibSetAddress(
            (__int64)qword_140026AE0,
            AddressPoolEntry + 40,
            a3,
            v16,
            *(_WORD *)(AddressPoolEntry + 58),
            0);
        }
        WinNatDereferenceAddressPoolEntry((PVOID)AddressPoolEntry);
      }
    }
    v3 = (PVOID *)*v3;
  }
  if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0zqhhxqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_ADDRESS_CHANGE_NOTIFY,
      a3,
      (unsigned int)&dword_14002198C,
      *(_DWORD *)(a1 + 8),
      0,
      0,
      *(_QWORD *)a1,
      3,
      v5);
}

```

## disassembly

```asm
0x14000f428  mov     [rsp+arg_8], rbx
0x14000f42d  mov     [rsp+arg_10], rbp
0x14000f432  push    rsi
0x14000f433  push    rdi
0x14000f434  push    r15
0x14000f436  sub     rsp, 290h
0x14000f43d  mov     rax, cs:__security_cookie
0x14000f444  xor     rax, rsp
0x14000f447  mov     [rsp+2A8h+var_28], rax
0x14000f44f  mov     rdi, cs:qword_140026B08
0x14000f456  lea     r15, qword_140026B08
0x14000f45d  mov     rsi, rcx
0x14000f460  xor     ebp, ebp
0x14000f462  jmp     loc_14000F53C
0x14000f467  mov     rbx, [rsi]
0x14000f46a  cmp     [rdi+10h], rbx
0x14000f46e  jnz     loc_14000F539
0x14000f474  xor     edx, edx; Val
0x14000f476  mov     [rsp+2A8h+var_258], 0
0x14000f47b  mov     r8d, 210h; Size
0x14000f481  lea     rcx, [rsp+2A8h+pszDest]; void *
0x14000f486  call    memset
0x14000f48b  mov     eax, [rsi+8]
0x14000f48e  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x14000f493  mov     r8, [rdi+20h]
0x14000f497  mov     [rsp+2A8h+var_30], eax
0x14000f49e  add     r8, 158h; pszSrc
0x14000f4a5  movzx   eax, word ptr [rdi+1Ah]
0x14000f4a9  mov     [rsp+2A8h+var_2A], ax
0x14000f4b1  movzx   eax, word ptr [rdi+18h]
0x14000f4b5  mov     [rsp+2A8h+var_2C], ax
0x14000f4bd  mov     [rsp+2A8h+var_38], rbx
0x14000f4c5  call    StringCchCopyW
0x14000f4ca  mov     ebp, eax
0x14000f4cc  test    eax, eax
0x14000f4ce  jns     short loc_14000F4D5
0x14000f4d0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f4d5  lea     rdx, [rsp+2A8h+var_258]
0x14000f4da  lea     rcx, [rsp+2A8h+pszDest]
0x14000f4df  call    WinNatFindAddressPoolEntry
0x14000f4e4  mov     rbx, rax
0x14000f4e7  test    rax, rax
0x14000f4ea  jz      short loc_14000F539
0x14000f4ec  cmp     [rsp+2A8h+var_258], 0
0x14000f4f1  jz      short loc_14000F4F8
0x14000f4f3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f4f8  mov     al, [rbx+48h]
0x14000f4fb  test    al, 2
0x14000f4fd  jz      short loc_14000F509
0x14000f4ff  mov     rcx, rbx; P
0x14000f502  call    WinNatDeleteAddressPoolEntry
0x14000f507  jmp     short loc_14000F531
0x14000f509  movzx   r9d, word ptr [rbx+38h]
0x14000f50e  lea     rdx, [rbx+28h]
0x14000f512  or      al, 1
0x14000f514  mov     byte ptr [rsp+2A8h+var_280], 0
0x14000f519  mov     [rbx+48h], al
0x14000f51c  movzx   eax, word ptr [rbx+3Ah]
0x14000f520  mov     rcx, cs:qword_140026AE0
0x14000f527  mov     word ptr [rsp+2A8h+var_288], ax
0x14000f52c  call    WinNatLibSetAddress
0x14000f531  mov     rcx, rbx; P
0x14000f534  call    WinNatDereferenceAddressPoolEntry
0x14000f539  mov     rdi, [rdi]
0x14000f53c  cmp     rdi, r15
0x14000f53f  jnz     loc_14000F467
0x14000f545  cmp     cs:dword_140026104, 1
0x14000f54c  jnz     short loc_14000F59A
0x14000f54e  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f555  jz      short loc_14000F59A
0x14000f557  mov     rax, [rsi]
0x14000f55a  lea     r9, dword_14002198C
0x14000f561  mov     [rsp+2A8h+var_260], ebp
0x14000f565  xor     ecx, ecx
0x14000f567  mov     [rsp+2A8h+var_268], 3
0x14000f56f  xor     edx, edx
0x14000f571  mov     [rsp+2A8h+var_270], rax
0x14000f576  mov     eax, [rsi+8]
0x14000f579  mov     [rsp+2A8h+var_278], cx
0x14000f57e  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f585  mov     [rsp+2A8h+var_280], dx
0x14000f58a  lea     rdx, WINNAT_ADDRESS_CHANGE_NOTIFY
0x14000f591  mov     [rsp+2A8h+var_288], eax
0x14000f595  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f59a  mov     rcx, [rsp+2A8h+var_28]
0x14000f5a2  xor     rcx, rsp; StackCookie
0x14000f5a5  call    __security_check_cookie
0x14000f5aa  lea     r11, [rsp+2A8h+var_18]
0x14000f5b2  mov     rbx, [r11+28h]
0x14000f5b6  mov     rbp, [r11+30h]
0x14000f5ba  mov     rsp, r11
0x14000f5bd  pop     r15
0x14000f5bf  pop     rdi
0x14000f5c0  pop     rsi
0x14000f5c1  retn
```
