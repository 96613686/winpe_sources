# TraceEnableClientA(x,x,x)

- ea: `0x100027e0`
- end: `0x10002860`
- name: `_TraceEnableClientA@12`
- size: `128`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x10002160`
- `0x10002470`
- `0x10009977`
- `0x10009b20`

## callees

- `0x100027e0`
- `0x10002870`
- `0x10006f22`
- `0x10006fac`
- `0x10006fd6`
- `0x10007715`

## pseudocode

```c
DWORD __fastcall TraceEnableClientA(int a1, _DWORD *a2, int a3)
{
  int v4; // edi
  char v5; // cl
  DWORD result; // eax
  int v8; // [esp+10h] [ebp-4h]

  v4 = 0;
  v8 = a2[8];
  v5 = v8;
  a2[8] = v8 & 0xFFFFFFFE;
  if ( (v8 & 8) != 0 )
  {
    result = TraceRegConfigClientA((int)a2, a3);
    if ( result )
      return result;
    v5 = v8;
  }
  if ( (a2[8] & 4) != 0 )
  {
    if ( a3 || (v5 & 4) == 0 )
    {
      result = TraceOpenClientConsoleA(a1, (int)a2);
      if ( result )
        return result;
      v5 = v8;
    }
    v4 = a2[61] | 4;
    if ( !a3 )
      goto LABEL_8;
  }
  else if ( !a3 )
  {
    if ( (v5 & 4) != 0 )
    {
      TraceCloseClientConsoleA(a1, a2);
      v5 = v8;
    }
LABEL_8:
    if ( (v5 & 2) != 0 )
      TraceCloseClientFileW(a2);
  }
  if ( (a2[8] & 2) == 0 )
  {
LABEL_11:
    _InterlockedExchange((volatile __int32 *)(a1 + 68 + 4 * a2[9]), v4);
    return 0;
  }
  result = TraceCreateClientFileA((int)a2);
  if ( !result )
  {
    v4 |= a2[60] | 2;
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x100027e0  mov     edi, edi
0x100027e2  push    ebp
0x100027e3  mov     ebp, esp
0x100027e5  sub     esp, 8
0x100027e8  push    ebx
0x100027e9  mov     ebx, [ebp+arg_0]
0x100027ec  push    esi
0x100027ed  mov     esi, edx
0x100027ef  mov     [ebp+var_8], ecx
0x100027f2  push    edi
0x100027f3  xor     edi, edi
0x100027f5  mov     ecx, [esi+20h]
0x100027f8  mov     eax, ecx
0x100027fa  and     eax, 0FFFFFFFEh
0x100027fd  mov     [ebp+var_4], ecx
0x10002800  mov     [esi+20h], eax
0x10002803  test    cl, 8
0x10002806  jz      short loc_10002818
0x10002808  mov     edx, ebx
0x1000280a  mov     ecx, esi
0x1000280c  call    _TraceRegConfigClientA@8; TraceRegConfigClientA(x,x)
0x10002811  test    eax, eax
0x10002813  jnz     short loc_1000284E
0x10002815  mov     ecx, [ebp+var_4]
0x10002818  test    byte ptr [esi+20h], 4
0x1000281c  jnz     loc_10005660
0x10002822  test    ebx, ebx
0x10002824  jnz     short loc_10002834
0x10002826  test    cl, 4
0x10002829  jnz     loc_10005694
0x1000282f  test    cl, 2
0x10002832  jnz     short loc_10002857
0x10002834  test    byte ptr [esi+20h], 2
0x10002838  jnz     loc_100056A6
0x1000283e  mov     ecx, [ebp+var_8]
0x10002841  mov     eax, [esi+24h]
0x10002844  add     ecx, 44h ; 'D'
0x10002847  lea     eax, [ecx+eax*4]
0x1000284a  xchg    edi, [eax]
0x1000284c  xor     eax, eax
0x1000284e  pop     edi
0x1000284f  pop     esi
0x10002850  pop     ebx
0x10002851  mov     esp, ebp
0x10002853  pop     ebp
0x10002854  retn    4
0x10002857  mov     ecx, esi
0x10002859  call    _TraceCloseClientFileW@4; TraceCloseClientFileW(x)
0x1000285e  jmp     short loc_10002834
0x10005660  test    ebx, ebx
0x10005662  jnz     short loc_10005669
0x10005664  test    cl, 4
0x10005667  jnz     short loc_1000567E
0x10005669  mov     ecx, [ebp+var_8]
0x1000566c  mov     edx, esi
0x1000566e  call    _TraceOpenClientConsoleA@8; TraceOpenClientConsoleA(x,x)
0x10005673  test    eax, eax
0x10005675  jnz     loc_1000284E
0x1000567b  mov     ecx, [ebp+var_4]
0x1000567e  mov     edi, [esi+0F4h]
0x10005684  or      edi, 4
0x10005687  test    ebx, ebx
0x10005689  jnz     loc_10002834
0x1000568f  jmp     loc_1000282F
0x10005694  mov     ecx, [ebp+var_8]
0x10005697  mov     edx, esi
0x10005699  call    _TraceCloseClientConsoleA@8; TraceCloseClientConsoleA(x,x)
0x1000569e  mov     ecx, [ebp+var_4]
0x100056a1  jmp     loc_1000282F
0x100056a6  mov     ecx, esi
0x100056a8  call    _TraceCreateClientFileA@4; TraceCreateClientFileA(x)
0x100056ad  test    eax, eax
0x100056af  jnz     loc_1000284E
0x100056b5  mov     eax, [esi+0F0h]
0x100056bb  or      eax, 2
0x100056be  or      edi, eax
0x100056c0  jmp     loc_1000283E
```
