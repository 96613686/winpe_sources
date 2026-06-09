# UpdateWeight

- ea: `0x180008780`
- end: `0x180008899`
- name: `UpdateWeight`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800067cc`

## callees

- `0x180008780`
- `0x180009770`
- `0x18001c9ec`

## pseudocode

```c
int __fastcall UpdateWeight(__int64 *a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // bx
  __int64 i; // r14
  __int16 v5; // si
  __int64 v6; // rax
  int v7; // edi
  bool v8; // zf
  __int64 v9; // rbp
  __int64 v10; // rcx
  int result; // eax
  __int16 v12; // bp

  v2 = a2;
  for ( i = *a1; v2 != 1; *(_DWORD *)(i + 4 * v10 + 8) = v7 + 1 )
  {
    v5 = v2 - 1;
    v6 = (__int16)(v2 - 1);
    v7 = *(_DWORD *)(i + 12LL * (__int16)v2 + 8);
    v8 = *(_DWORD *)(i + 12 * v6 + 8) == v7;
    v9 = i + 12 * v6;
    if ( *(_DWORD *)(v9 + 8) < v7 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v8 = *(_DWORD *)(v9 + 8) == v7;
    }
    if ( v8 )
    {
      do
        v12 = v5--;
      while ( *(_DWORD *)(i + 12LL * v5 + 8) == v7 );
      if ( v12 >= 1 )
      {
        if ( v12 > 1 )
        {
          SwapNodes(a1, v2, (unsigned __int16)v12);
          v2 = v12;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
    v10 = 3LL * (__int16)v2;
    v2 = *(_WORD *)(i + 12LL * (__int16)v2);
  }
  ++*(_DWORD *)(i + 12LL * v2 + 8);
  result = *(_DWORD *)(i + 12LL * *(__int16 *)(i + 12LL * v2 + 2) + 8)
         + *(_DWORD *)(i + 12LL * *(__int16 *)(i + 12LL * v2 + 4) + 8);
  if ( *(_DWORD *)(i + 12LL * v2 + 8) != result )
    return MicrosoftTelemetryAssertTriggeredNoArgs();
  return result;
}

```

## disassembly

```asm
0x180008780  sub     rsp, 38h
0x180008784  mov     [rsp+38h+arg_0], rbx
0x180008789  movzx   ebx, dx
0x18000878c  mov     [rsp+38h+var_10], r14
0x180008791  mov     r14, [rcx]
0x180008794  mov     [rsp+38h+var_18], r15
0x180008799  mov     r15, rcx
0x18000879c  cmp     dx, 1
0x1800087a0  jz      short loc_180008808
0x1800087a2  mov     [rsp+38h+arg_8], rbp
0x1800087a7  mov     [rsp+38h+arg_10], rsi
0x1800087ac  mov     [rsp+38h+var_8], rdi
0x1800087b1  movsx   rax, bx
0x1800087b5  lea     esi, [rbx-1]
0x1800087b8  lea     rcx, [rax+rax*2]
0x1800087bc  movsx   rax, si
0x1800087c0  mov     edi, [r14+rcx*4+8]
0x1800087c5  lea     rcx, [rax+rax*2]
0x1800087c9  cmp     [r14+rcx*4+8], edi
0x1800087ce  lea     rbp, [r14+rcx*4]
0x1800087d2  jge     short loc_1800087DC
0x1800087d4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800087d9  cmp     [rbp+8], edi
0x1800087dc  jz      short loc_180008850
0x1800087de  movsx   rax, bx
0x1800087e2  lea     rcx, [rax+rax*2]
0x1800087e6  movzx   ebx, word ptr [r14+rcx*4]
0x1800087eb  lea     eax, [rdi+1]
0x1800087ee  mov     [r14+rcx*4+8], eax
0x1800087f3  cmp     bx, 1
0x1800087f7  jnz     short loc_1800087B1
0x1800087f9  mov     rdi, [rsp+38h+var_8]
0x1800087fe  mov     rsi, [rsp+38h+arg_10]
0x180008803  mov     rbp, [rsp+38h+arg_8]
0x180008808  mov     r15, [rsp+38h+var_18]
0x18000880d  movzx   eax, bx
0x180008810  mov     rbx, [rsp+38h+arg_0]
0x180008815  lea     rcx, [rax+rax*2]
0x180008819  inc     dword ptr [r14+rcx*4+8]
0x18000881e  movsx   rax, word ptr [r14+rcx*4+4]
0x180008824  mov     r8d, [r14+rcx*4+8]
0x180008829  lea     rdx, [rax+rax*2]
0x18000882d  movsx   rax, word ptr [r14+rcx*4+2]
0x180008833  lea     rcx, [rax+rax*2]
0x180008837  mov     eax, [r14+rdx*4+8]
0x18000883c  add     eax, [r14+rcx*4+8]
0x180008841  mov     r14, [rsp+38h+var_10]
0x180008846  cmp     r8d, eax
0x180008849  jnz     short loc_180008892
0x18000884b  add     rsp, 38h
0x18000884f  retn
0x180008850  movzx   ebp, si
0x180008853  dec     si
0x180008856  movsx   rax, si
0x18000885a  lea     rcx, [rax+rax*2]
0x18000885e  cmp     [r14+rcx*4+8], edi
0x180008863  jz      short loc_180008850
0x180008865  cmp     bp, 1
0x180008869  jge     short loc_180008875
0x18000886b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008870  jmp     loc_1800087DE
0x180008875  jle     loc_1800087DE
0x18000887b  movzx   r8d, bp
0x18000887f  movzx   edx, bx
0x180008882  mov     rcx, r15
0x180008885  call    SwapNodes
0x18000888a  movzx   ebx, bp
0x18000888d  jmp     loc_1800087DE
0x180008892  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008897  jmp     short loc_18000884B
```
