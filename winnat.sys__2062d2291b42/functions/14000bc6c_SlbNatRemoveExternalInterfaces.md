# SlbNatRemoveExternalInterfaces

- ea: `0x14000bc6c`
- end: `0x14000bd94`
- name: `SlbNatRemoveExternalInterfaces`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002f380`
- `0x140030b2c`

## callees

- `0x14000bc6c`
- `0x140014548`
- `0x140032228`

## pseudocode

```c
void __fastcall SlbNatRemoveExternalInterfaces(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  char *v5; // rbx
  char *v7; // r14
  char *v8; // rax
  char **v9; // rcx

  v3 = a1 + 24;
  v5 = *(char **)(a1 + 24);
  if ( v5 != (char *)(a1 + 24) )
  {
    do
    {
      v7 = *(char **)v5;
      if ( !a2 || *(_DWORD *)(a2 + 8) == *((_DWORD *)v5 + 14) )
      {
        if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer(
            &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)WINNATM_INSTANCE_EXTERNAL_INTERFACE_ASSOCIATION,
            a3,
            (const wchar_t *)(a1 + 80),
            a1 + 164,
            *(_BYTE *)(a1 + 182),
            *(_DWORD *)(a1 + 184),
            *(_DWORD *)(a1 + 68),
            *(_DWORD *)(a1 + 272),
            *(_DWORD *)(a1 + 200),
            *(_DWORD *)(a1 + 212),
            *(_DWORD *)(a1 + 216),
            *(_DWORD *)(a1 + 224),
            *(_DWORD *)(a1 + 220),
            *(_DWORD *)(a1 + 208),
            *(_BYTE *)(a1 + 204));
        v8 = *(char **)v5;
        if ( *(char **)(*(_QWORD *)v5 + 8LL) != v5 || (v9 = (char **)*((_QWORD *)v5 + 1), *v9 != v5) )
          __fastfail(3u);
        *v9 = v8;
        *((_QWORD *)v8 + 1) = v9;
        SlbNatDeleteExternalAddress(v5, a1);
      }
      v5 = v7;
    }
    while ( v7 != (char *)v3 );
  }
}

```

## disassembly

```asm
0x14000bc6c  push    rbx
0x14000bc6e  push    rbp
0x14000bc6f  push    rsi
0x14000bc70  push    rdi
0x14000bc71  push    r14
0x14000bc73  sub     rsp, 80h
0x14000bc7a  lea     rsi, [rcx+18h]
0x14000bc7e  mov     rbp, rdx
0x14000bc81  mov     rbx, [rsi]
0x14000bc84  mov     rdi, rcx
0x14000bc87  cmp     rbx, rsi
0x14000bc8a  jz      loc_14000BD7E
0x14000bc90  mov     r14, [rbx]
0x14000bc93  test    rbp, rbp
0x14000bc96  jz      short loc_14000BCA4
0x14000bc98  mov     ecx, [rbp+8]
0x14000bc9b  cmp     ecx, [rbx+38h]
0x14000bc9e  jnz     loc_14000BD72
0x14000bca4  cmp     cs:dword_140027104, 1
0x14000bcab  jnz     loc_14000BD4E
0x14000bcb1  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000bcb8  jz      loc_14000BD4E
0x14000bcbe  movzx   eax, byte ptr [rdi+0CCh]
0x14000bcc5  lea     rdx, [rdi+0A4h]
0x14000bccc  movzx   ecx, byte ptr [rdi+0B6h]
0x14000bcd3  lea     r9, [rdi+50h]
0x14000bcd7  mov     [rsp+0A8h+var_30], eax
0x14000bcdb  mov     eax, [rdi+0D0h]
0x14000bce1  mov     [rsp+0A8h+var_38], eax
0x14000bce5  mov     eax, [rdi+0DCh]
0x14000bceb  mov     [rsp+0A8h+var_40], eax
0x14000bcef  mov     eax, [rdi+0E0h]
0x14000bcf5  mov     [rsp+0A8h+var_48], eax
0x14000bcf9  mov     eax, [rdi+0D8h]
0x14000bcff  mov     [rsp+0A8h+var_50], eax
0x14000bd03  mov     eax, [rdi+0D4h]
0x14000bd09  mov     [rsp+0A8h+var_58], eax
0x14000bd0d  mov     eax, [rdi+0C8h]
0x14000bd13  mov     [rsp+0A8h+var_60], eax
0x14000bd17  mov     eax, [rdi+110h]
0x14000bd1d  mov     [rsp+0A8h+var_68], eax
0x14000bd21  mov     eax, [rdi+44h]
0x14000bd24  mov     [rsp+0A8h+var_70], eax
0x14000bd28  mov     eax, [rdi+0B8h]
0x14000bd2e  mov     [rsp+0A8h+var_78], eax
0x14000bd32  mov     [rsp+0A8h+var_80], ecx
0x14000bd36  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000bd3d  mov     [rsp+0A8h+var_88], rdx
0x14000bd42  lea     rdx, WINNATM_INSTANCE_EXTERNAL_INTERFACE_ASSOCIATION
0x14000bd49  call    McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer
0x14000bd4e  mov     rax, [rbx]
0x14000bd51  cmp     [rax+8], rbx
0x14000bd55  jnz     short loc_14000BD8D
0x14000bd57  mov     rcx, [rbx+8]
0x14000bd5b  cmp     [rcx], rbx
0x14000bd5e  jnz     short loc_14000BD8D
0x14000bd60  mov     [rcx], rax
0x14000bd63  mov     rdx, rdi
0x14000bd66  mov     [rax+8], rcx
0x14000bd6a  mov     rcx, rbx; P
0x14000bd6d  call    SlbNatDeleteExternalAddress
0x14000bd72  mov     rbx, r14
0x14000bd75  cmp     r14, rsi
0x14000bd78  jnz     loc_14000BC90
0x14000bd7e  add     rsp, 80h
0x14000bd85  pop     r14
0x14000bd87  pop     rdi
0x14000bd88  pop     rsi
0x14000bd89  pop     rbp
0x14000bd8a  pop     rbx
0x14000bd8b  retn
0x14000bd8d  mov     ecx, 3
0x14000bd92  int     29h; Win8: RtlFailFast(ecx)
```
