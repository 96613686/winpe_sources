# GroupSubordinateInterfacesByUFD

- ea: `0x140028008`
- end: `0x1400281a4`
- name: `GroupSubordinateInterfacesByUFD`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027dcc`

## callees

- `0x14000a6cc`
- `0x14000c2bc`
- `0x140028008`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x140028033`
- `USBD!USBD_ParseDescriptors` at `0x140028033`

## pseudocode

```c
__int64 __fastcall GroupSubordinateInterfacesByUFD(_QWORD **a1, __int64 a2)
{
  unsigned __int8 *v2; // r8
  __int64 v4; // rdi
  unsigned __int8 *v5; // rsi
  PUSB_COMMON_DESCRIPTOR v7; // rax
  int v8; // edx
  unsigned int v9; // ecx
  unsigned __int8 *p_bLength; // rbx
  __int64 bLength; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rsi
  _QWORD *i; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rax
  _QWORD *v17; // r8
  _QWORD *v18; // r8
  int v19; // edx

  v2 = *(unsigned __int8 **)(a2 + 32);
  v4 = *(unsigned __int16 *)(a2 + 40);
  v5 = v2;
  do
  {
    v7 = USBD_ParseDescriptors(v5, v4, v2, 36);
    v9 = 0;
    p_bLength = &v7->bLength;
    if ( !v7 )
      break;
    bLength = v7->bLength;
    if ( (unsigned __int8)bLength < 3u )
      return (unsigned int)-1073741811;
    v2 = &p_bLength[bLength];
    if ( &p_bLength[bLength] > &v5[v4] )
      return (unsigned int)-1073741811;
  }
  while ( p_bLength[2] != 6 );
  if ( !p_bLength )
    return v9;
  if ( *p_bLength < 4u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        g_RecorderLog,
        v8,
        8,
        15,
        (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids,
        *(_BYTE *)(*(_QWORD *)(a2 + 32) + 2LL));
    }
    return (unsigned int)-1073741811;
  }
  v12 = *p_bLength - 4LL;
  if ( *p_bLength != 4 )
  {
    v13 = 0;
    do
    {
      for ( i = *a1; i != a1; i = (_QWORD *)*i )
      {
        v15 = i[4];
        if ( *(_BYTE *)(v15 + 2) == p_bLength[v13 + 4] )
        {
          if ( ((*(_BYTE *)(v15 + 5) - 2) & 0xF7) == 0 )
          {
            v16 = (_QWORD *)*i;
            if ( *(_QWORD **)(*i + 8LL) != i
              || (v17 = (_QWORD *)i[1], (_QWORD *)*v17 != i)
              || (*v17 = v16, v16[1] = v17, v18 = *(_QWORD **)(a2 + 24), *v18 != a2 + 16) )
            {
              __fastfail(3u);
            }
            *i = a2 + 16;
            i[1] = v18;
            *v18 = i;
            *(_QWORD *)(a2 + 24) = i;
          }
          goto LABEL_22;
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = p_bLength[v13 + 4];
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_dd(
          g_RecorderLog,
          v19,
          8,
          14,
          (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids,
          *(_BYTE *)(*(_QWORD *)(a2 + 32) + 2LL),
          p_bLength[v13 + 4]);
      }
      v9 = -1073741811;
LABEL_22:
      ++v13;
    }
    while ( v13 < v12 );
  }
  return v9;
}

```

## disassembly

```asm
0x140028008  push    rbx
0x14002800a  push    rbp
0x14002800b  push    rsi
0x14002800c  push    rdi
0x14002800d  push    r12
0x14002800f  push    r14
0x140028011  push    r15
0x140028013  sub     rsp, 40h
0x140028017  mov     r8, [rdx+20h]; StartPosition
0x14002801b  mov     rbp, rdx
0x14002801e  movzx   edi, word ptr [rdx+28h]
0x140028022  mov     rsi, r8
0x140028025  mov     r12, rcx
0x140028028  mov     r9d, 24h ; '$'; DescriptorType
0x14002802e  mov     edx, edi; TotalLength
0x140028030  mov     rcx, rsi; DescriptorBuffer
0x140028033  call    cs:__imp_USBD_ParseDescriptors
0x14002803a  nop     dword ptr [rax+rax+00h]
0x14002803f  xor     ecx, ecx
0x140028041  mov     rbx, rax
0x140028044  test    rax, rax
0x140028047  jz      short loc_14002806B
0x140028049  movzx   eax, byte ptr [rax]
0x14002804c  cmp     al, 3
0x14002804e  jb      loc_14002818D
0x140028054  lea     r8, [rbx+rax]
0x140028058  lea     rax, [rsi+rdi]
0x14002805c  cmp     r8, rax
0x14002805f  ja      loc_14002818D
0x140028065  cmp     byte ptr [rbx+2], 6
0x140028069  jnz     short loc_140028028
0x14002806b  test    rbx, rbx
0x14002806e  jz      loc_140028192
0x140028074  movzx   eax, byte ptr [rbx]
0x140028077  cmp     al, 4
0x140028079  jb      loc_14002814D
0x14002807f  mov     r14d, eax
0x140028082  sub     r14, 4
0x140028086  jz      loc_140028192
0x14002808c  xor     esi, esi
0x14002808e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140028095  lea     r15, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x14002809c  mov     rdx, [r12]
0x1400280a0  cmp     rdx, r12
0x1400280a3  jz      short loc_1400280F8
0x1400280a5  mov     r8, [rdx+20h]
0x1400280a9  mov     al, [rbx+rsi+4]
0x1400280ad  cmp     [r8+2], al
0x1400280b1  jz      short loc_1400280B8
0x1400280b3  mov     rdx, [rdx]
0x1400280b6  jmp     short loc_1400280A0
0x1400280b8  mov     al, [r8+5]
0x1400280bc  sub     al, 2
0x1400280be  test    al, 0F7h
0x1400280c0  jnz     short loc_140028138
0x1400280c2  mov     rax, [rdx]
0x1400280c5  cmp     [rax+8], rdx
0x1400280c9  jnz     short loc_140028146
0x1400280cb  mov     r8, [rdx+8]
0x1400280cf  cmp     [r8], rdx
0x1400280d2  jnz     short loc_140028146
0x1400280d4  mov     [r8], rax
0x1400280d7  mov     [rax+8], r8
0x1400280db  lea     rax, [rbp+10h]
0x1400280df  mov     r8, [rax+8]
0x1400280e3  cmp     [r8], rax
0x1400280e6  jnz     short loc_140028146
0x1400280e8  mov     [rdx], rax
0x1400280eb  mov     [rdx+8], r8
0x1400280ef  mov     [r8], rdx
0x1400280f2  mov     [rax+8], rdx
0x1400280f6  jmp     short loc_140028138
0x1400280f8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400280ff  jz      short loc_140028133
0x140028101  movzx   edx, byte ptr [rbx+rsi+4]
0x140028106  mov     r9d, 0Eh
0x14002810c  mov     rax, [rbp+20h]
0x140028110  mov     [rsp+78h+var_48], edx
0x140028114  mov     dl, 2
0x140028116  lea     r8d, [r9-6]
0x14002811a  movzx   ecx, byte ptr [rax+2]
0x14002811e  mov     [rsp+78h+var_50], ecx
0x140028122  mov     rcx, cs:g_RecorderLog
0x140028129  mov     [rsp+78h+var_58], r15
0x14002812e  call    WPP_RECORDER_SF_dd
0x140028133  mov     ecx, 0C000000Dh
0x140028138  inc     rsi
0x14002813b  cmp     rsi, r14
0x14002813e  jb      loc_14002809C
0x140028144  jmp     short loc_140028192
0x140028146  mov     ecx, 3
0x14002814b  int     29h; Win8: RtlFailFast(ecx)
0x14002814d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140028154  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002815b  jz      short loc_14002818D
0x14002815d  mov     rax, [rbp+20h]
0x140028161  lea     r15, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x140028168  mov     r9d, 0Fh
0x14002816e  mov     dl, 2
0x140028170  movzx   ecx, byte ptr [rax+2]
0x140028174  mov     [rsp+78h+var_50], ecx
0x140028178  lea     r8d, [r9-7]
0x14002817c  mov     rcx, cs:g_RecorderLog
0x140028183  mov     [rsp+78h+var_58], r15
0x140028188  call    WPP_RECORDER_SF_d
0x14002818d  mov     ecx, 0C000000Dh
0x140028192  mov     eax, ecx
0x140028194  add     rsp, 40h
0x140028198  pop     r15
0x14002819a  pop     r14
0x14002819c  pop     r12
0x14002819e  pop     rdi
0x14002819f  pop     rsi
0x1400281a0  pop     rbp
0x1400281a1  pop     rbx
0x1400281a2  retn
```
