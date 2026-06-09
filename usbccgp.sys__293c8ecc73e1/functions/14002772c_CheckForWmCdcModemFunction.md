# CheckForWmCdcModemFunction

- ea: `0x14002772c`
- end: `0x1400278d4`
- name: `CheckForWmCdcModemFunction`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027dcc`

## callees

- `0x14000a6cc`
- `0x14002772c`
- `0x1400278dc`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x14002776b`
- `USBD!USBD_ParseDescriptors` at `0x1400277f5`
- `USBD!USBD_ParseDescriptors` at `0x14002776b`
- `USBD!USBD_ParseDescriptors` at `0x1400277f5`

## pseudocode

```c
__int64 __fastcall CheckForWmCdcModemFunction(__int64 a1, _BYTE *a2)
{
  char *v2; // rdi
  unsigned int v3; // ebx
  PUSB_COMMON_DESCRIPTOR v6; // rax
  int v7; // edx
  __int64 *v8; // rcx
  __int64 v9; // r13
  char *v10; // rdi
  char v11; // bp
  char v12; // si
  unsigned __int8 v13; // r14
  unsigned __int8 *v14; // rax
  PUSB_COMMON_DESCRIPTOR v15; // rax
  __int64 bLength; // rdx

  v2 = *(char **)(a1 + 32);
  v3 = 0;
  *a2 = 0;
  if ( v2[6] == 2 && v2[4] == 1 )
  {
    v6 = USBD_ParseDescriptors(v2, *(unsigned __int16 *)(a1 + 40), v2, 5);
    if ( v6 && v6->bLength >= 7u )
    {
      if ( (v6[1].bDescriptorType & 3) == 3
        && (v6[1].bLength & 0x80u) != 0
        && (unsigned __int8)CountListEntries(a1 + 16) == 1 )
      {
        v9 = *v8;
        v10 = *(char **)(*v8 + 32);
        if ( v10[5] == 10 && v10[4] == 2 )
        {
          v11 = 0;
          v12 = 0;
          v13 = 0;
          v14 = *(unsigned __int8 **)(*v8 + 32);
          while ( 1 )
          {
            v3 = 0;
            if ( v13 >= (unsigned __int8)v10[4] )
              break;
            v15 = USBD_ParseDescriptors(v10, *(unsigned __int16 *)(v9 + 40), v14, 5);
            if ( !v15 || (bLength = v15->bLength, (unsigned __int8)bLength < 7u) )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(bLength) = 2;
                WPP_RECORDER_SF_d(
                  g_RecorderLog,
                  bLength,
                  8,
                  16,
                  (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids,
                  v10[2]);
              }
              v3 = -1073741811;
              break;
            }
            if ( (v15[1].bDescriptorType & 3) == 2 )
            {
              if ( (v15[1].bLength & 0x80u) == 0 )
                ++v12;
              else
                ++v11;
            }
            v14 = &v15->bLength + bLength;
            ++v13;
          }
          if ( v11 == 1 && v12 == 1 )
            *a2 = 1;
        }
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(g_RecorderLog, v7, 8, 17, (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids, v2[2]);
      }
      return (unsigned int)-1073741811;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14002772c  push    rbx
0x14002772e  push    rbp
0x14002772f  push    rsi
0x140027730  push    rdi
0x140027731  push    r13
0x140027733  push    r14
0x140027735  push    r15
0x140027737  sub     rsp, 30h
0x14002773b  mov     rdi, [rcx+20h]
0x14002773f  xor     ebx, ebx
0x140027741  mov     r15, rdx
0x140027744  mov     [rdx], bl
0x140027746  mov     rsi, rcx
0x140027749  cmp     byte ptr [rdi+6], 2
0x14002774d  jnz     loc_1400278C2
0x140027753  cmp     byte ptr [rdi+4], 1
0x140027757  jnz     loc_1400278C2
0x14002775d  movzx   edx, word ptr [rcx+28h]; TotalLength
0x140027761  lea     r9d, [rbx+5]; DescriptorType
0x140027765  mov     rcx, rdi; DescriptorBuffer
0x140027768  mov     r8, rdi; StartPosition
0x14002776b  call    cs:__imp_USBD_ParseDescriptors
0x140027772  nop     dword ptr [rax+rax+00h]
0x140027777  mov     rcx, rax
0x14002777a  test    rax, rax
0x14002777d  jz      loc_140027881
0x140027783  cmp     byte ptr [rax], 7
0x140027786  jb      loc_140027881
0x14002778c  mov     al, [rax+3]
0x14002778f  and     al, 3
0x140027791  cmp     al, 3
0x140027793  jnz     loc_1400278C2
0x140027799  cmp     [rcx+2], bl
0x14002779c  jge     loc_1400278C2
0x1400277a2  lea     rcx, [rsi+10h]
0x1400277a6  call    CountListEntries
0x1400277ab  cmp     al, 1
0x1400277ad  jnz     loc_1400278C2
0x1400277b3  mov     r13, [rcx]
0x1400277b6  mov     rdi, [r13+20h]
0x1400277ba  cmp     byte ptr [rdi+5], 0Ah
0x1400277be  jnz     loc_1400278C2
0x1400277c4  cmp     byte ptr [rdi+4], 2
0x1400277c8  jnz     loc_1400278C2
0x1400277ce  xor     bpl, bpl
0x1400277d1  xor     sil, sil
0x1400277d4  xor     r14b, r14b
0x1400277d7  mov     rax, rdi
0x1400277da  xor     ebx, ebx
0x1400277dc  cmp     r14b, [rdi+4]
0x1400277e0  jnb     loc_140027871
0x1400277e6  movzx   edx, word ptr [r13+28h]; TotalLength
0x1400277eb  lea     r9d, [rbx+5]; DescriptorType
0x1400277ef  mov     r8, rax; StartPosition
0x1400277f2  mov     rcx, rdi; DescriptorBuffer
0x1400277f5  call    cs:__imp_USBD_ParseDescriptors
0x1400277fc  nop     dword ptr [rax+rax+00h]
0x140027801  mov     rcx, rax
0x140027804  test    rax, rax
0x140027807  jz      short loc_140027830
0x140027809  movzx   edx, byte ptr [rax]
0x14002780c  cmp     dl, 7
0x14002780f  jb      short loc_140027830
0x140027811  mov     al, [rax+3]
0x140027814  and     al, 3
0x140027816  cmp     al, 2
0x140027818  jnz     short loc_140027827
0x14002781a  cmp     [rcx+2], bl
0x14002781d  jge     short loc_140027824
0x14002781f  inc     bpl
0x140027822  jmp     short loc_140027827
0x140027824  inc     sil
0x140027827  lea     rax, [rcx+rdx]
0x14002782b  inc     r14b
0x14002782e  jmp     short loc_1400277DA
0x140027830  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027837  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002783e  jz      short loc_14002786C
0x140027840  movzx   eax, byte ptr [rdi+2]
0x140027844  mov     r9d, 10h
0x14002784a  mov     rcx, cs:g_RecorderLog
0x140027851  mov     dl, 2
0x140027853  mov     [rsp+68h+var_40], eax
0x140027857  lea     rax, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x14002785e  mov     [rsp+68h+var_48], rax
0x140027863  lea     r8d, [r9-8]
0x140027867  call    WPP_RECORDER_SF_d
0x14002786c  mov     ebx, 0C000000Dh
0x140027871  cmp     bpl, 1
0x140027875  jnz     short loc_1400278C2
0x140027877  cmp     sil, bpl
0x14002787a  jnz     short loc_1400278C2
0x14002787c  mov     [r15], bpl
0x14002787f  jmp     short loc_1400278C2
0x140027881  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027888  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002788f  jz      short loc_1400278BD
0x140027891  movzx   eax, byte ptr [rdi+2]
0x140027895  mov     r9d, 11h
0x14002789b  mov     rcx, cs:g_RecorderLog
0x1400278a2  mov     dl, 2
0x1400278a4  mov     [rsp+68h+var_40], eax
0x1400278a8  lea     rax, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x1400278af  mov     [rsp+68h+var_48], rax
0x1400278b4  lea     r8d, [r9-9]
0x1400278b8  call    WPP_RECORDER_SF_d
0x1400278bd  mov     ebx, 0C000000Dh
0x1400278c2  mov     eax, ebx
0x1400278c4  add     rsp, 30h
0x1400278c8  pop     r15
0x1400278ca  pop     r14
0x1400278cc  pop     r13
0x1400278ce  pop     rdi
0x1400278cf  pop     rsi
0x1400278d0  pop     rbp
0x1400278d1  pop     rbx
0x1400278d2  retn
```
