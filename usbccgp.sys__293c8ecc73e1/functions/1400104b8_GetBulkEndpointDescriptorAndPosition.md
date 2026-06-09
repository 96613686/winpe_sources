# GetBulkEndpointDescriptorAndPosition

- ea: `0x1400104b8`
- end: `0x14001056c`
- name: `GetBulkEndpointDescriptorAndPosition`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400019d8`

## callees

- `0x1400104b8`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x1400104fc`
- `USBD!USBD_ParseDescriptors` at `0x1400104fc`

## pseudocode

```c
__int64 __fastcall GetBulkEndpointDescriptorAndPosition(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        PUSB_COMMON_DESCRIPTOR *a4,
        _DWORD *a5)
{
  int v6; // ebx
  int v8; // esi
  unsigned int v9; // edi
  PUSB_COMMON_DESCRIPTOR v12; // rdx
  unsigned __int8 *v13; // r15
  PUSB_COMMON_DESCRIPTOR v14; // rax
  __int64 result; // rax

  v6 = 0;
  v8 = 0;
  v9 = 0;
  v12 = 0;
  v13 = a2 + 4;
  while ( v9 < *v13 )
  {
    v14 = USBD_ParseDescriptors(
            *(PVOID *)(*(_QWORD *)(a1 + 232) + 56LL),
            *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 232) + 56LL) + 2LL),
            a2,
            5);
    v12 = v14;
    if ( !v14 )
      return 3221226021LL;
    if ( a3 == v9 )
      break;
    if ( (v14[1].bDescriptorType & 3) == 2 )
    {
      if ( (v14[1].bLength & 0x80u) == 0 )
        ++v8;
      else
        ++v6;
    }
    ++v9;
    a2 = &v14->bLength + v14->bLength;
  }
  if ( (v12[1].bDescriptorType & 3) != 2 )
    return 3221226021LL;
  if ( (v12[1].bLength & 0x80u) == 0 )
    v6 = v8;
  *a5 = v6;
  result = 0;
  *a4 = v12;
  return result;
}

```

## disassembly

```asm
0x1400104b8  push    rbx
0x1400104ba  push    rbp
0x1400104bb  push    rsi
0x1400104bc  push    rdi
0x1400104bd  push    r13
0x1400104bf  push    r14
0x1400104c1  push    r15
0x1400104c3  sub     rsp, 20h
0x1400104c7  mov     ebp, r8d
0x1400104ca  xor     ebx, ebx
0x1400104cc  mov     r8, rdx; StartPosition
0x1400104cf  xor     esi, esi
0x1400104d1  xor     edi, edi
0x1400104d3  mov     r14, r9
0x1400104d6  mov     r13, rcx
0x1400104d9  xor     edx, edx
0x1400104db  lea     r15, [r8+4]
0x1400104df  movzx   eax, byte ptr [r15]
0x1400104e3  cmp     edi, eax
0x1400104e5  jnb     short loc_14001053D
0x1400104e7  mov     rax, [r13+0E8h]
0x1400104ee  mov     r9d, 5; DescriptorType
0x1400104f4  mov     rcx, [rax+38h]; DescriptorBuffer
0x1400104f8  movzx   edx, word ptr [rcx+2]; TotalLength
0x1400104fc  call    cs:__imp_USBD_ParseDescriptors
0x140010503  nop     dword ptr [rax+rax+00h]
0x140010508  mov     rdx, rax
0x14001050b  test    rax, rax
0x14001050e  jz      short loc_140010536
0x140010510  cmp     ebp, edi
0x140010512  jz      short loc_14001053D
0x140010514  mov     cl, [rax+3]
0x140010517  and     cl, 3
0x14001051a  cmp     cl, 2
0x14001051d  jnz     short loc_14001052B
0x14001051f  cmp     byte ptr [rax+2], 0
0x140010523  jge     short loc_140010529
0x140010525  inc     ebx
0x140010527  jmp     short loc_14001052B
0x140010529  inc     esi
0x14001052b  movzx   r8d, byte ptr [rax]
0x14001052f  inc     edi
0x140010531  add     r8, rax
0x140010534  jmp     short loc_1400104DF
0x140010536  mov     eax, 0C0000225h
0x14001053b  jmp     short loc_14001055C
0x14001053d  mov     al, [rdx+3]
0x140010540  and     al, 3
0x140010542  cmp     al, 2
0x140010544  jnz     short loc_140010536
0x140010546  cmp     byte ptr [rdx+2], 0
0x14001054a  mov     rax, [rsp+58h+arg_20]
0x140010552  cmovge  ebx, esi
0x140010555  mov     [rax], ebx
0x140010557  xor     eax, eax
0x140010559  mov     [r14], rdx
0x14001055c  add     rsp, 20h
0x140010560  pop     r15
0x140010562  pop     r14
0x140010564  pop     r13
0x140010566  pop     rdi
0x140010567  pop     rsi
0x140010568  pop     rbp
0x140010569  pop     rbx
0x14001056a  retn
```
