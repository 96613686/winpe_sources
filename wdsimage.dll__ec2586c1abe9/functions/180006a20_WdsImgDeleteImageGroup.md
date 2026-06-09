# WdsImgDeleteImageGroup

- ea: `0x180006a20`
- end: `0x180006a94`
- name: `WdsImgDeleteImageGroup`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006714`
- `0x180006810`
- `0x180006a20`

## import_xrefs

- `WdsCommonLib!WdsDeleteDirectory` at `0x180006a49`
- `WdsCommonLib!WdsDeleteDirectory` at `0x180006a49`

## pseudocode

```c
__int64 __fastcall WdsImgDeleteImageGroup(__int64 a1)
{
  unsigned int v1; // ebx
  int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8

  v1 = 0;
  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 2 )
    {
      v2 = WdsDeleteDirectory(*(_QWORD *)(a1 + 32));
      if ( (unsigned int)ElValidateWin32_0((unsigned int)v2, v3, v4, 336) )
      {
        if ( v2 > 0 )
          v1 = (unsigned __int16)v2 | 0x80070000;
        else
          v1 = v2;
      }
      ElValidateHr_1(v1, v5, v6, 898);
    }
    else
    {
      return (unsigned int)-1056833019;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x180006a20  mov     [rsp+arg_0], rbx
0x180006a25  push    rdi
0x180006a26  sub     rsp, 20h
0x180006a2a  xor     ebx, ebx
0x180006a2c  test    rcx, rcx
0x180006a2f  jnz     short loc_180006A38
0x180006a31  mov     ebx, 80070057h
0x180006a36  jmp     short loc_180006A86
0x180006a38  cmp     dword ptr [rcx+10h], 2
0x180006a3c  jz      short loc_180006A45
0x180006a3e  mov     ebx, 0C1020205h
0x180006a43  jmp     short loc_180006A86
0x180006a45  mov     rcx, [rcx+20h]
0x180006a49  call    cs:__imp_WdsDeleteDirectory
0x180006a50  nop     dword ptr [rax+rax+00h]
0x180006a55  mov     ecx, eax
0x180006a57  mov     r9d, 150h
0x180006a5d  mov     edi, eax
0x180006a5f  call    ElValidateWin32_0
0x180006a64  test    eax, eax
0x180006a66  jz      short loc_180006A79
0x180006a68  test    edi, edi
0x180006a6a  jg      short loc_180006A70
0x180006a6c  mov     ebx, edi
0x180006a6e  jmp     short loc_180006A79
0x180006a70  movzx   ebx, di
0x180006a73  or      ebx, 80070000h
0x180006a79  mov     r9d, 382h
0x180006a7f  mov     ecx, ebx
0x180006a81  call    ElValidateHr_1
0x180006a86  mov     eax, ebx
0x180006a88  mov     rbx, [rsp+28h+arg_0]
0x180006a8d  add     rsp, 20h
0x180006a91  pop     rdi
0x180006a92  retn
```
