# SRV2_PERF_ISSUE_RECEIVE_CORRELATION

- ea: `0x140019ab8`
- end: `0x140019bf4`
- name: `SRV2_PERF_ISSUE_RECEIVE_CORRELATION`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140074ad0`

## callees

- `0x140019ab8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140019b48`
- `ntoskrnl!EtwWriteTransfer` at `0x140019b98`
- `ntoskrnl!EtwWriteTransfer` at `0x140019be6`
- `ntoskrnl!EtwWriteTransfer` at `0x140019b48`
- `ntoskrnl!EtwWriteTransfer` at `0x140019b98`
- `ntoskrnl!EtwWriteTransfer` at `0x140019be6`

## pseudocode

```c
void __fastcall SRV2_PERF_ISSUE_RECEIVE_CORRELATION(__int64 a1)
{
  __int64 v2; // rdx
  unsigned __int16 v3; // ax
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // r8

  if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    if ( *(_BYTE *)(a1 + 600) )
    {
      v2 = *(_QWORD *)(a1 + 304);
      if ( v2 )
      {
        v3 = *(_WORD *)(v2 + 22);
        if ( v3 )
        {
          v4 = 0;
          if ( v3 > 1u )
          {
            do
            {
              v5 = v4 + 1;
              EtwWriteTransfer(
                PROV_SRV2_Context,
                &SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER,
                (LPCGUID)(16LL * v4 + v2 + 100),
                (LPCGUID)(v2 + 16LL * (v4 + 1) + 100),
                0,
                0);
              v2 = *(_QWORD *)(a1 + 304);
              v4 = v5;
            }
            while ( v5 + 1 < *(unsigned __int16 *)(v2 + 22) );
          }
          EtwWriteTransfer(
            PROV_SRV2_Context,
            &SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER,
            (LPCGUID)(16LL * v4 + v2 + 100),
            (LPCGUID)(a1 + 584),
            0,
            0);
          v6 = *(_QWORD *)(a1 + 416);
          if ( v6 )
          {
            if ( v6 != a1 )
              EtwWriteTransfer(
                PROV_SRV2_Context,
                &SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER,
                (LPCGUID)(v6 + 584),
                (LPCGUID)(a1 + 584),
                0,
                0);
          }
          *(_WORD *)(*(_QWORD *)(a1 + 304) + 22LL) = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140019ab8  mov     [rsp+arg_0], rbx
0x140019abd  mov     [rsp+arg_8], rsi
0x140019ac2  push    rdi
0x140019ac3  sub     rsp, 30h
0x140019ac7  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140019ace  mov     rdi, rcx
0x140019ad1  jz      short loc_140019AF3
0x140019ad3  xor     esi, esi
0x140019ad5  cmp     [rcx+258h], sil
0x140019adc  jz      short loc_140019AF3
0x140019ade  mov     rdx, [rcx+130h]
0x140019ae5  test    rdx, rdx
0x140019ae8  jz      short loc_140019AF3
0x140019aea  movzx   eax, word ptr [rdx+16h]
0x140019aee  test    ax, ax
0x140019af1  jnz     short loc_140019B04
0x140019af3  mov     rbx, [rsp+38h+arg_0]
0x140019af8  mov     rsi, [rsp+38h+arg_8]
0x140019afd  add     rsp, 30h
0x140019b01  pop     rdi
0x140019b02  retn
0x140019b04  mov     ecx, 1
0x140019b09  mov     r8d, esi
0x140019b0c  cmp     cx, ax
0x140019b0f  jnb     short loc_140019B69
0x140019b11  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140019b18  lea     ebx, [r8+1]
0x140019b1c  mov     eax, r8d
0x140019b1f  lea     r8, [rdx+64h]
0x140019b23  shl     rax, 4
0x140019b27  mov     r9d, ebx
0x140019b2a  add     r8, rax; ActivityId
0x140019b2d  shl     r9, 4
0x140019b31  add     r9, 64h ; 'd'
0x140019b35  mov     [rsp+38h+UserData], rsi; UserData
0x140019b3a  add     r9, rdx; RelatedActivityId
0x140019b3d  mov     [rsp+38h+UserDataCount], esi; UserDataCount
0x140019b41  lea     rdx, SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER; EventDescriptor
0x140019b48  call    cs:__imp_EtwWriteTransfer
0x140019b4f  nop     dword ptr [rax+rax+00h]
0x140019b54  mov     rdx, [rdi+130h]
0x140019b5b  lea     eax, [rbx+1]
0x140019b5e  mov     r8d, ebx
0x140019b61  movzx   ecx, word ptr [rdx+16h]
0x140019b65  cmp     eax, ecx
0x140019b67  jb      short loc_140019B11
0x140019b69  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140019b70  lea     rbx, [rdi+248h]
0x140019b77  mov     eax, r8d
0x140019b7a  mov     r9, rbx; RelatedActivityId
0x140019b7d  lea     r8, [rdx+64h]
0x140019b81  shl     rax, 4
0x140019b85  add     r8, rax; ActivityId
0x140019b88  mov     [rsp+38h+UserData], rsi; UserData
0x140019b8d  lea     rdx, SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER; EventDescriptor
0x140019b94  mov     [rsp+38h+UserDataCount], esi; UserDataCount
0x140019b98  call    cs:__imp_EtwWriteTransfer
0x140019b9f  nop     dword ptr [rax+rax+00h]
0x140019ba4  mov     r8, [rdi+1A0h]
0x140019bab  test    r8, r8
0x140019bae  jnz     short loc_140019BC0
0x140019bb0  mov     rcx, [rdi+130h]
0x140019bb7  mov     [rcx+16h], si
0x140019bbb  jmp     loc_140019AF3
0x140019bc0  cmp     r8, rdi
0x140019bc3  jz      short loc_140019BB0
0x140019bc5  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140019bcc  lea     rdx, SMB2_EVENT_WORKITEM_ACTIVITY_TRANSFER; EventDescriptor
0x140019bd3  add     r8, 248h; ActivityId
0x140019bda  mov     [rsp+38h+UserData], rsi; UserData
0x140019bdf  mov     r9, rbx; RelatedActivityId
0x140019be2  mov     [rsp+38h+UserDataCount], esi; UserDataCount
0x140019be6  call    cs:__imp_EtwWriteTransfer
0x140019bed  nop     dword ptr [rax+rax+00h]
0x140019bf2  jmp     short loc_140019BB0
```
