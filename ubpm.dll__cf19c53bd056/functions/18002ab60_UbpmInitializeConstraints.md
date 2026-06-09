# UbpmInitializeConstraints

- ea: `0x18002ab60`
- end: `0x18002ac9b`
- name: `UbpmInitializeConstraints`
- size: `315`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a7f0`

## callees

- `0x18002ab60`
- `0x180030cec`
- `0x18003d810`

## import_xrefs

- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x18002abf4`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x18002abf4`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002ac72`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002ac72`

## pseudocode

```c
__int64 UbpmInitializeConstraints()
{
  __int64 i; // rbx
  __int64 v1; // rcx
  unsigned int v2; // esi
  int WellKnownEvent; // eax
  unsigned int v4; // edi
  __int64 j; // rdx
  __int64 k; // rbx
  __int128 v8; // [rsp+30h] [rbp-79h]
  __int128 v9; // [rsp+40h] [rbp-69h]
  _OWORD v10[3]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v11; // [rsp+A0h] [rbp-9h]
  _BYTE v12[36]; // [rsp+B0h] [rbp+7h] BYREF
  int v13; // [rsp+D4h] [rbp+2Bh]

  memset(v12, 0, sizeof(v12));
  v13 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 5 )
    {
      for ( j = 0; j != 5; ++j )
      {
        *(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)((char *)&g_CSebConditions + 28 * j + 20) = *(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)&v12[8 * j];
        *(_QWORD *)&v12[8 * j] = 0;
      }
      v4 = 0;
      goto LABEL_11;
    }
    v1 = 28LL * (unsigned int)i;
    *(_QWORD *)&v8 = 0;
    v9 = 0;
    v10[2] = 0;
    v11 = 0;
    v2 = *(_DWORD *)((char *)&g_CSebConditions + v1 + 4);
    HIDWORD(v8) = *(_DWORD *)((char *)&g_CSebConditions + v1);
    DWORD1(v9) = *(_DWORD *)((char *)&g_CSebConditions + v1 + 8);
    DWORD2(v8) = v2;
    v10[1] = v9;
    v10[0] = v8;
    WellKnownEvent = CSebCreateWellKnownEvent(v10, &v12[8 * i]);
    if ( WellKnownEvent < 0 )
      break;
  }
  v4 = 10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_029c709143543b8b7778781675a35e95_Traceguids,
      v2,
      WellKnownEvent);
LABEL_11:
  for ( k = 0; k != 5; ++k )
  {
    if ( *(_DWORD *)&v12[8 * k] || *(_DWORD *)&v12[8 * k + 4] )
      CSebDeleteEvent(*(_QWORD *)&v12[8 * k]);
  }
  return v4;
}

```

## disassembly

```asm
0x18002ab60  push    rbp
0x18002ab62  push    rbx
0x18002ab63  push    rsi
0x18002ab64  push    rdi
0x18002ab65  lea     rbp, [rsp-3Fh]
0x18002ab6a  sub     rsp, 0E8h
0x18002ab71  mov     rax, cs:__security_cookie
0x18002ab78  xor     rax, rsp
0x18002ab7b  mov     [rbp+57h+var_28], rax
0x18002ab7f  xorps   xmm0, xmm0
0x18002ab82  mov     dword ptr [rbp+57h+var_50], 0
0x18002ab89  xor     eax, eax
0x18002ab8b  lea     rdi, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002ab92  movups  xmmword ptr [rbp+57h+var_50+4], xmm0
0x18002ab96  mov     [rbp+57h+var_2C], eax
0x18002ab99  xor     ebx, ebx
0x18002ab9b  movups  [rbp+57h+var_3C], xmm0
0x18002ab9f  cmp     ebx, 5
0x18002aba2  jnb     loc_18002AC3B
0x18002aba8  xorps   xmm2, xmm2
0x18002abab  mov     edx, ebx
0x18002abad  imul    rcx, rdx, 1Ch
0x18002abb1  movups  [rbp+57h+var_D0], xmm2
0x18002abb5  movups  [rbp+57h+var_C0], xmm2
0x18002abb9  xor     r8d, r8d
0x18002abbc  movaps  [rbp+57h+var_70], xmm2
0x18002abc0  mov     [rbp+57h+var_60], r8
0x18002abc4  mov     eax, [rcx+rdi]
0x18002abc7  mov     esi, [rcx+rdi+4]
0x18002abcb  mov     dword ptr [rbp+57h+var_D0+0Ch], eax
0x18002abce  mov     eax, [rcx+rdi+8]
0x18002abd2  lea     rcx, [rbp+57h+var_90]
0x18002abd6  mov     dword ptr [rbp+57h+var_C0+4], eax
0x18002abd9  lea     rax, [rbp+57h+var_50]
0x18002abdd  movups  xmm1, [rbp+57h+var_C0]
0x18002abe1  mov     dword ptr [rbp+57h+var_D0+8], esi
0x18002abe4  lea     rdx, [rax+rbx*8]
0x18002abe8  movups  xmm0, [rbp+57h+var_D0]
0x18002abec  movaps  [rbp+57h+var_80], xmm1
0x18002abf0  movaps  [rbp+57h+var_90], xmm0
0x18002abf4  call    cs:__imp_CSebCreateWellKnownEvent
0x18002abfa  test    eax, eax
0x18002abfc  js      short loc_18002AC02
0x18002abfe  inc     ebx
0x18002ac00  jmp     short loc_18002AB9F
0x18002ac02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac09  lea     rdx, WPP_GLOBAL_Control
0x18002ac10  mov     edi, 0Ah
0x18002ac15  cmp     rcx, rdx
0x18002ac18  jz      short loc_18002AC5D
0x18002ac1a  test    byte ptr [rcx+1Ch], 1
0x18002ac1e  jz      short loc_18002AC5D
0x18002ac20  mov     rcx, [rcx+10h]
0x18002ac24  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x18002ac2b  mov     edx, edi
0x18002ac2d  mov     [rsp+100h+var_E0], eax
0x18002ac31  mov     r9d, esi
0x18002ac34  call    WPP_SF_dd
0x18002ac39  jmp     short loc_18002AC5D
0x18002ac3b  xor     edx, edx
0x18002ac3d  mov     rax, [rbp+rdx*8+57h+var_50]
0x18002ac42  imul    rcx, rdx, 1Ch
0x18002ac46  mov     [rcx+rdi+14h], rax
0x18002ac4b  xor     eax, eax
0x18002ac4d  mov     [rbp+rdx*8+57h+var_50], rax
0x18002ac52  inc     rdx
0x18002ac55  cmp     rdx, 5
0x18002ac59  jnz     short loc_18002AC3D
0x18002ac5b  xor     edi, edi
0x18002ac5d  xor     ebx, ebx
0x18002ac5f  cmp     dword ptr [rbp+rbx*8+57h+var_50], 0
0x18002ac64  jnz     short loc_18002AC6D
0x18002ac66  cmp     dword ptr [rbp+rbx*8+57h+var_50+4], 0
0x18002ac6b  jz      short loc_18002AC78
0x18002ac6d  mov     rcx, [rbp+rbx*8+57h+var_50]
0x18002ac72  call    cs:__imp_CSebDeleteEvent
0x18002ac78  inc     rbx
0x18002ac7b  cmp     rbx, 5
0x18002ac7f  jnz     short loc_18002AC5F
0x18002ac81  mov     eax, edi
0x18002ac83  mov     rcx, [rbp+57h+var_28]
0x18002ac87  xor     rcx, rsp; StackCookie
0x18002ac8a  call    __security_check_cookie
0x18002ac8f  add     rsp, 0E8h
0x18002ac96  pop     rdi
0x18002ac97  pop     rsi
0x18002ac98  pop     rbx
0x18002ac99  pop     rbp
0x18002ac9a  retn
```
