# Write255Short

- ea: `0x18000ecc8`
- end: `0x18000ed6a`
- name: `Write255Short`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d5a0`

## callees

- `0x18000ecc8`
- `0x18001c9ec`

## pseudocode

```c
_BYTE *__fastcall Write255Short(_BYTE **a1, __int16 a2)
{
  _BYTE *v2; // rbx
  __int16 v4; // di
  bool v5; // cf
  _BYTE *v6; // rbx
  _BYTE *result; // rax

  v2 = *a1;
  LOBYTE(v4) = a2;
  if ( (unsigned int)(a2 + 249) <= 0x3E6 )
  {
    if ( a2 < 0 )
    {
      *v2 = -6;
      v4 = -a2;
    }
    else
    {
      v5 = (unsigned __int16)a2 < 0xFAu;
      if ( a2 < 250 )
        goto LABEL_4;
      v4 = a2 - 250;
      if ( (__int16)(a2 - 250) < 250 )
      {
        *v2 = -1;
      }
      else
      {
        v4 = a2 - 500;
        *v2 = -2;
      }
    }
    ++v2;
    if ( v4 < 0 )
    {
LABEL_9:
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_10;
    }
    v5 = (unsigned __int16)v4 < 0xFAu;
LABEL_4:
    if ( v5 )
      goto LABEL_10;
    goto LABEL_9;
  }
  *v2 = -3;
  v6 = v2 + 1;
  *v6 = HIBYTE(a2);
  v2 = v6 + 1;
LABEL_10:
  result = v2 + 1;
  *v2 = v4;
  *a1 = v2 + 1;
  return result;
}

```

## disassembly

```asm
0x18000ecc8  mov     [rsp+arg_0], rbx
0x18000eccd  mov     [rsp+arg_8], rsi
0x18000ecd2  push    rdi
0x18000ecd3  sub     rsp, 20h
0x18000ecd7  mov     rbx, [rcx]
0x18000ecda  mov     rsi, rcx
0x18000ecdd  movsx   edi, dx
0x18000ece0  lea     eax, [rdi+0F9h]
0x18000ece6  cmp     eax, 3E6h
0x18000eceb  ja      short loc_18000ED00
0x18000eced  mov     eax, 0FAh
0x18000ecf2  test    di, di
0x18000ecf5  js      short loc_18000ED19
0x18000ecf7  cmp     di, ax
0x18000ecfa  jge     short loc_18000ED50
0x18000ecfc  jnb     short loc_18000ED2C
0x18000ecfe  jmp     short loc_18000ED31
0x18000ed00  mov     byte ptr [rbx], 0FDh
0x18000ed03  mov     ecx, 1
0x18000ed08  add     rbx, rcx
0x18000ed0b  movzx   eax, di
0x18000ed0e  sar     ax, 8
0x18000ed12  mov     [rbx], al
0x18000ed14  add     rbx, rcx
0x18000ed17  jmp     short loc_18000ED31
0x18000ed19  mov     byte ptr [rbx], 0FAh
0x18000ed1c  neg     di
0x18000ed1f  mov     ecx, 1
0x18000ed24  add     rbx, rcx
0x18000ed27  test    di, di
0x18000ed2a  jns     short loc_18000ED4B
0x18000ed2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ed31  lea     rax, [rbx+1]
0x18000ed35  mov     [rbx], dil
0x18000ed38  mov     rbx, [rsp+28h+arg_0]
0x18000ed3d  mov     [rsi], rax
0x18000ed40  mov     rsi, [rsp+28h+arg_8]
0x18000ed45  add     rsp, 20h
0x18000ed49  pop     rdi
0x18000ed4a  retn
0x18000ed4b  cmp     di, ax
0x18000ed4e  jmp     short loc_18000ECFC
0x18000ed50  mov     ecx, 0FFFFFF06h
0x18000ed55  add     di, cx
0x18000ed58  cmp     di, ax
0x18000ed5b  jl      short loc_18000ED65
0x18000ed5d  add     di, cx
0x18000ed60  mov     byte ptr [rbx], 0FEh
0x18000ed63  jmp     short loc_18000ED1F
0x18000ed65  mov     byte ptr [rbx], 0FFh
0x18000ed68  jmp     short loc_18000ED1F
```
