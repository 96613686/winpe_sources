# UbpmInitializeConstraints

- ea: `0x18002c7f4`
- end: `0x18002c93c`
- name: `UbpmInitializeConstraints`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002c420`

## callees

- `0x18002c7f4`
- `0x180032f78`
- `0x180040260`

## import_xrefs

- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x18002c888`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x18002c888`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002c90c`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002c90c`

## pseudocode

```c
__int64 UbpmInitializeConstraints()
{
  __int64 i; // rbx
  __int64 v1; // rcx
  unsigned int v2; // esi
  unsigned int v3; // edi
  __int64 j; // rdx
  __int64 k; // rbx
  __int128 v7; // [rsp+30h] [rbp-79h]
  __int128 v8; // [rsp+40h] [rbp-69h]
  _OWORD v9[3]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v10; // [rsp+A0h] [rbp-9h]
  _BYTE v11[36]; // [rsp+B0h] [rbp+7h] BYREF
  int v12; // [rsp+D4h] [rbp+2Bh]

  memset(v11, 0, sizeof(v11));
  v12 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 5 )
    {
      for ( j = 0; j != 5; ++j )
      {
        *(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)((char *)&g_CSebConditions + 28 * j + 20) = *(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)&v11[8 * j];
        *(_QWORD *)&v11[8 * j] = 0;
      }
      v3 = 0;
      goto LABEL_11;
    }
    v1 = 28LL * (unsigned int)i;
    *(_QWORD *)&v7 = 0;
    v8 = 0;
    v9[2] = 0;
    v10 = 0;
    v2 = *(_DWORD *)((char *)&g_CSebConditions + v1 + 4);
    HIDWORD(v7) = *(_DWORD *)((char *)&g_CSebConditions + v1);
    DWORD1(v8) = *(_DWORD *)((char *)&g_CSebConditions + v1 + 8);
    DWORD2(v7) = v2;
    v9[1] = v8;
    v9[0] = v7;
    if ( (int)CSebCreateWellKnownEvent(v9, &v11[8 * i]) < 0 )
      break;
  }
  v3 = 10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_029c709143543b8b7778781675a35e95_Traceguids, v2);
LABEL_11:
  for ( k = 0; k != 5; ++k )
  {
    if ( *(_DWORD *)&v11[8 * k] || *(_DWORD *)&v11[8 * k + 4] )
      CSebDeleteEvent(*(_QWORD *)&v11[8 * k]);
  }
  return v3;
}

```

## disassembly

```asm
0x18002c7f4  push    rbp
0x18002c7f6  push    rbx
0x18002c7f7  push    rsi
0x18002c7f8  push    rdi
0x18002c7f9  lea     rbp, [rsp-3Fh]
0x18002c7fe  sub     rsp, 0E8h
0x18002c805  mov     rax, cs:__security_cookie
0x18002c80c  xor     rax, rsp
0x18002c80f  mov     [rbp+57h+var_28], rax
0x18002c813  xorps   xmm0, xmm0
0x18002c816  mov     dword ptr [rbp+57h+var_50], 0
0x18002c81d  xor     eax, eax
0x18002c81f  lea     rdi, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002c826  movups  xmmword ptr [rbp+57h+var_50+4], xmm0
0x18002c82a  mov     [rbp+57h+var_2C], eax
0x18002c82d  xor     ebx, ebx
0x18002c82f  movups  [rbp+57h+var_3C], xmm0
0x18002c833  cmp     ebx, 5
0x18002c836  jnb     loc_18002C8D5
0x18002c83c  xorps   xmm2, xmm2
0x18002c83f  mov     edx, ebx
0x18002c841  imul    rcx, rdx, 1Ch
0x18002c845  movups  [rbp+57h+var_D0], xmm2
0x18002c849  movups  [rbp+57h+var_C0], xmm2
0x18002c84d  xor     r8d, r8d
0x18002c850  movaps  [rbp+57h+var_70], xmm2
0x18002c854  mov     [rbp+57h+var_60], r8
0x18002c858  mov     eax, [rcx+rdi]
0x18002c85b  mov     esi, [rcx+rdi+4]
0x18002c85f  mov     dword ptr [rbp+57h+var_D0+0Ch], eax
0x18002c862  mov     eax, [rcx+rdi+8]
0x18002c866  lea     rcx, [rbp+57h+var_90]
0x18002c86a  mov     dword ptr [rbp+57h+var_C0+4], eax
0x18002c86d  lea     rax, [rbp+57h+var_50]
0x18002c871  movups  xmm1, [rbp+57h+var_C0]
0x18002c875  mov     dword ptr [rbp+57h+var_D0+8], esi
0x18002c878  lea     rdx, [rax+rbx*8]
0x18002c87c  movups  xmm0, [rbp+57h+var_D0]
0x18002c880  movaps  [rbp+57h+var_80], xmm1
0x18002c884  movaps  [rbp+57h+var_90], xmm0
0x18002c888  call    cs:__imp_CSebCreateWellKnownEvent
0x18002c88f  nop     dword ptr [rax+rax+00h]
0x18002c894  test    eax, eax
0x18002c896  js      short loc_18002C89C
0x18002c898  inc     ebx
0x18002c89a  jmp     short loc_18002C833
0x18002c89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8a3  lea     rdx, WPP_GLOBAL_Control
0x18002c8aa  mov     edi, 0Ah
0x18002c8af  cmp     rcx, rdx
0x18002c8b2  jz      short loc_18002C8F7
0x18002c8b4  test    byte ptr [rcx+1Ch], 1
0x18002c8b8  jz      short loc_18002C8F7
0x18002c8ba  mov     rcx, [rcx+10h]
0x18002c8be  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x18002c8c5  mov     edx, edi
0x18002c8c7  mov     [rsp+100h+var_E0], eax
0x18002c8cb  mov     r9d, esi
0x18002c8ce  call    WPP_SF_dd
0x18002c8d3  jmp     short loc_18002C8F7
0x18002c8d5  xor     edx, edx
0x18002c8d7  mov     rax, [rbp+rdx*8+57h+var_50]
0x18002c8dc  imul    rcx, rdx, 1Ch
0x18002c8e0  mov     [rcx+rdi+14h], rax
0x18002c8e5  xor     eax, eax
0x18002c8e7  mov     [rbp+rdx*8+57h+var_50], rax
0x18002c8ec  inc     rdx
0x18002c8ef  cmp     rdx, 5
0x18002c8f3  jnz     short loc_18002C8D7
0x18002c8f5  xor     edi, edi
0x18002c8f7  xor     ebx, ebx
0x18002c8f9  cmp     dword ptr [rbp+rbx*8+57h+var_50], 0
0x18002c8fe  jnz     short loc_18002C907
0x18002c900  cmp     dword ptr [rbp+rbx*8+57h+var_50+4], 0
0x18002c905  jz      short loc_18002C918
0x18002c907  mov     rcx, [rbp+rbx*8+57h+var_50]
0x18002c90c  call    cs:__imp_CSebDeleteEvent
0x18002c913  nop     dword ptr [rax+rax+00h]
0x18002c918  inc     rbx
0x18002c91b  cmp     rbx, 5
0x18002c91f  jnz     short loc_18002C8F9
0x18002c921  mov     eax, edi
0x18002c923  mov     rcx, [rbp+57h+var_28]
0x18002c927  xor     rcx, rsp; StackCookie
0x18002c92a  call    __security_check_cookie
0x18002c92f  add     rsp, 0E8h
0x18002c936  pop     rdi
0x18002c937  pop     rsi
0x18002c938  pop     rbx
0x18002c939  pop     rbp
0x18002c93a  retn
```
