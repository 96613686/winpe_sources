# WinNatDeleteAddressFromPool

- ea: `0x14000f480`
- end: `0x14000f61b`
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
- `0x14000e6a8`
- `0x14000e8ec`
- `0x14000f480`
- `0x14000f624`
- `0x14000f954`
- `0x140010610`
- `0x140019adc`
- `0x14001f320`
- `0x14001f980`

## pseudocode

```c
void __fastcall WinNatDeleteAddressFromPool(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v3; // rdi
  char v5; // bp
  PVOID v6; // rbx
  const wchar_t *v7; // r8
  size_t v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 AddressPoolEntry; // rbx
  char v16; // al
  int v17; // r9d
  char v18[16]; // [rsp+50h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-248h] BYREF
  PVOID v20; // [rsp+270h] [rbp-38h]
  int v21; // [rsp+278h] [rbp-30h]
  __int16 v22; // [rsp+27Ch] [rbp-2Ch]
  __int16 v23; // [rsp+27Eh] [rbp-2Ah]

  v3 = (PVOID *)qword_140027B08;
  v5 = 0;
  while ( v3 != &qword_140027B08 )
  {
    v6 = *(PVOID *)a1;
    if ( v3[2] == *(PVOID *)a1 )
    {
      v18[0] = 0;
      memset(pszDest, 0, sizeof(pszDest));
      v7 = (const wchar_t *)v3[4];
      v21 = *(_DWORD *)(a1 + 8);
      v23 = *((_WORD *)v3 + 13);
      v22 = *((_WORD *)v3 + 12);
      v20 = v6;
      v9 = StringCchCopyW(pszDest, v8, v7 + 172);
      v5 = v9;
      if ( v9 < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10, v12);
      AddressPoolEntry = WinNatFindAddressPoolEntry(pszDest, v18);
      if ( AddressPoolEntry )
      {
        if ( v18[0] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, a3);
        v16 = *(_BYTE *)(AddressPoolEntry + 72);
        if ( (v16 & 2) != 0 )
        {
          WinNatDeleteAddressPoolEntry((PVOID)AddressPoolEntry);
        }
        else
        {
          v17 = *(unsigned __int16 *)(AddressPoolEntry + 56);
          *(_BYTE *)(AddressPoolEntry + 72) = v16 | 1;
          WinNatLibSetAddress(
            (_DWORD)qword_140027AE0,
            AddressPoolEntry + 40,
            a3,
            v17,
            *(_WORD *)(AddressPoolEntry + 58),
            0);
        }
        WinNatDereferenceAddressPoolEntry((PVOID)AddressPoolEntry);
      }
    }
    v3 = (PVOID *)*v3;
  }
  if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0zqhhxqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_ADDRESS_CHANGE_NOTIFY,
      a3,
      (unsigned int)&dword_140021E9C,
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
0x14000f480  mov     [rsp+arg_8], rbx
0x14000f485  mov     [rsp+arg_10], rbp
0x14000f48a  push    rsi
0x14000f48b  push    rdi
0x14000f48c  push    r15
0x14000f48e  sub     rsp, 290h
0x14000f495  mov     rax, cs:__security_cookie
0x14000f49c  xor     rax, rsp
0x14000f49f  mov     [rsp+2A8h+var_28], rax
0x14000f4a7  mov     rdi, cs:qword_140027B08
0x14000f4ae  lea     r15, qword_140027B08
0x14000f4b5  mov     rsi, rcx
0x14000f4b8  xor     ebp, ebp
0x14000f4ba  jmp     loc_14000F594
0x14000f4bf  mov     rbx, [rsi]
0x14000f4c2  cmp     [rdi+10h], rbx
0x14000f4c6  jnz     loc_14000F591
0x14000f4cc  xor     edx, edx; Val
0x14000f4ce  mov     [rsp+2A8h+var_258], 0
0x14000f4d3  mov     r8d, 210h; Size
0x14000f4d9  lea     rcx, [rsp+2A8h+pszDest]; void *
0x14000f4de  call    memset
0x14000f4e3  mov     eax, [rsi+8]
0x14000f4e6  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x14000f4eb  mov     r8, [rdi+20h]
0x14000f4ef  mov     [rsp+2A8h+var_30], eax
0x14000f4f6  add     r8, 158h; pszSrc
0x14000f4fd  movzx   eax, word ptr [rdi+1Ah]
0x14000f501  mov     [rsp+2A8h+var_2A], ax
0x14000f509  movzx   eax, word ptr [rdi+18h]
0x14000f50d  mov     [rsp+2A8h+var_2C], ax
0x14000f515  mov     [rsp+2A8h+var_38], rbx
0x14000f51d  call    StringCchCopyW
0x14000f522  mov     ebp, eax
0x14000f524  test    eax, eax
0x14000f526  jns     short loc_14000F52D
0x14000f528  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f52d  lea     rdx, [rsp+2A8h+var_258]
0x14000f532  lea     rcx, [rsp+2A8h+pszDest]
0x14000f537  call    WinNatFindAddressPoolEntry
0x14000f53c  mov     rbx, rax
0x14000f53f  test    rax, rax
0x14000f542  jz      short loc_14000F591
0x14000f544  cmp     [rsp+2A8h+var_258], 0
0x14000f549  jz      short loc_14000F550
0x14000f54b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f550  mov     al, [rbx+48h]
0x14000f553  test    al, 2
0x14000f555  jz      short loc_14000F561
0x14000f557  mov     rcx, rbx; P
0x14000f55a  call    WinNatDeleteAddressPoolEntry
0x14000f55f  jmp     short loc_14000F589
0x14000f561  movzx   r9d, word ptr [rbx+38h]
0x14000f566  lea     rdx, [rbx+28h]
0x14000f56a  or      al, 1
0x14000f56c  mov     byte ptr [rsp+2A8h+var_280], 0
0x14000f571  mov     [rbx+48h], al
0x14000f574  movzx   eax, word ptr [rbx+3Ah]
0x14000f578  mov     rcx, cs:qword_140027AE0
0x14000f57f  mov     word ptr [rsp+2A8h+var_288], ax
0x14000f584  call    WinNatLibSetAddress
0x14000f589  mov     rcx, rbx; P
0x14000f58c  call    WinNatDereferenceAddressPoolEntry
0x14000f591  mov     rdi, [rdi]
0x14000f594  cmp     rdi, r15
0x14000f597  jnz     loc_14000F4BF
0x14000f59d  cmp     cs:dword_140027104, 1
0x14000f5a4  jnz     short loc_14000F5F2
0x14000f5a6  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f5ad  jz      short loc_14000F5F2
0x14000f5af  mov     rax, [rsi]
0x14000f5b2  lea     r9, dword_140021E9C
0x14000f5b9  mov     [rsp+2A8h+var_260], ebp
0x14000f5bd  xor     ecx, ecx
0x14000f5bf  mov     [rsp+2A8h+var_268], 3
0x14000f5c7  xor     edx, edx
0x14000f5c9  mov     [rsp+2A8h+var_270], rax
0x14000f5ce  mov     eax, [rsi+8]
0x14000f5d1  mov     [rsp+2A8h+var_278], cx
0x14000f5d6  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f5dd  mov     [rsp+2A8h+var_280], dx
0x14000f5e2  lea     rdx, WINNAT_ADDRESS_CHANGE_NOTIFY
0x14000f5e9  mov     [rsp+2A8h+var_288], eax
0x14000f5ed  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f5f2  mov     rcx, [rsp+2A8h+var_28]
0x14000f5fa  xor     rcx, rsp; StackCookie
0x14000f5fd  call    __security_check_cookie
0x14000f602  lea     r11, [rsp+2A8h+var_18]
0x14000f60a  mov     rbx, [r11+28h]
0x14000f60e  mov     rbp, [r11+30h]
0x14000f612  mov     rsp, r11
0x14000f615  pop     r15
0x14000f617  pop     rdi
0x14000f618  pop     rsi
0x14000f619  retn
```
