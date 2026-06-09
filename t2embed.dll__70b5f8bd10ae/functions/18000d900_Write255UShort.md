# Write255UShort

- ea: `0x18000d900`
- end: `0x18000d997`
- name: `Write255UShort`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800059a0`
- `0x18000bd00`
- `0x18000d5a0`

## callees

- `0x18000d900`
- `0x18001c9ec`

## pseudocode

```c
_BYTE *__fastcall Write255UShort(char **a1, __int16 a2)
{
  char *v2; // rax
  __int16 v3; // bx
  char *v4; // rdi
  _BYTE *result; // rax
  char v7; // cl

  v2 = *a1;
  LOBYTE(v3) = a2;
  v4 = *a1;
  if ( a2 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_5;
  }
  if ( a2 >= 759 )
  {
    *v2 = -3;
    v2[1] = HIBYTE(a2);
    v4 = v2 + 2;
    goto LABEL_6;
  }
  if ( a2 >= 253 )
  {
    v3 = a2 - 253;
    ++v4;
    if ( (__int16)(a2 - 253) < 253 )
    {
      v7 = -1;
    }
    else
    {
      v3 = a2 - 506;
      v7 = -2;
    }
    *v2 = v7;
    if ( v3 < 0 || v3 >= 253 )
LABEL_5:
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_6:
  result = v4 + 1;
  *v4 = v3;
  *a1 = v4 + 1;
  return result;
}

```

## disassembly

```asm
0x18000d900  mov     [rsp+arg_0], rbx
0x18000d905  mov     [rsp+arg_8], rsi
0x18000d90a  push    rdi
0x18000d90b  sub     rsp, 20h
0x18000d90f  mov     rax, [rcx]
0x18000d912  movzx   ebx, dx
0x18000d915  mov     rdi, rax
0x18000d918  mov     rsi, rcx
0x18000d91b  test    dx, dx
0x18000d91e  js      short loc_18000D964
0x18000d920  mov     ecx, 2F7h
0x18000d925  cmp     dx, cx
0x18000d928  jl      short loc_18000D96B
0x18000d92a  lea     rdi, [rax+1]
0x18000d92e  mov     byte ptr [rax], 0FDh
0x18000d931  movzx   eax, dx
0x18000d934  shr     ax, 8
0x18000d938  mov     [rdi], al
0x18000d93a  inc     rdi
0x18000d93d  jmp     short loc_18000D94B
0x18000d93f  mov     [rax], cl
0x18000d941  test    bx, bx
0x18000d944  jns     short loc_18000D990
0x18000d946  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d94b  lea     rax, [rdi+1]
0x18000d94f  mov     [rdi], bl
0x18000d951  mov     rbx, [rsp+28h+arg_0]
0x18000d956  mov     [rsi], rax
0x18000d959  mov     rsi, [rsp+28h+arg_8]
0x18000d95e  add     rsp, 20h
0x18000d962  pop     rdi
0x18000d963  retn
0x18000d964  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d969  jmp     short loc_18000D946
0x18000d96b  mov     edx, 0FDh
0x18000d970  cmp     bx, dx
0x18000d973  jl      short loc_18000D94B
0x18000d975  mov     ecx, 0FFFFFF03h
0x18000d97a  add     bx, cx
0x18000d97d  inc     rdi
0x18000d980  cmp     bx, dx
0x18000d983  jl      short loc_18000D98C
0x18000d985  add     bx, cx
0x18000d988  mov     cl, 0FEh
0x18000d98a  jmp     short loc_18000D93F
0x18000d98c  mov     cl, 0FFh
0x18000d98e  jmp     short loc_18000D93F
0x18000d990  cmp     bx, dx
0x18000d993  jl      short loc_18000D94B
0x18000d995  jmp     short loc_18000D946
```
