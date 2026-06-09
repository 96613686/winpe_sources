# HUBUCX_UpdateDeviceInfoUsingUCXIoctl

- ea: `0x140029104`
- end: `0x1400292bc`
- name: `HUBUCX_UpdateDeviceInfoUsingUCXIoctl`
- size: `440`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140024840`

## callees

- `0x1400024b8`
- `0x140025ce8`
- `0x1400284dc`
- `0x140029104`
- `0x14002dc90`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
__int64 __fastcall HUBUCX_UpdateDeviceInfoUsingUCXIoctl(__int64 *a1)
{
  __int64 v2; // rbx
  _DWORD *v3; // rsi
  unsigned int v4; // r8d
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  __int64 result; // rax
  int v9; // edx
  int v10; // [rsp+28h] [rbp-10h]

  v2 = *a1;
  v3 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
                   WdfDriverGlobals,
                   a1[55],
                   0);
  memset(v3, 0, 0x48u);
  v3[6] |= 0xBu;
  v4 = v3[6] & 0xFFFFFFFB;
  if ( (*(_BYTE *)(v2 + 2512) & 4) == 0 )
    v4 = v3[6] | 4;
  v3[6] = v4;
  if ( (*((_DWORD *)a1 + 413) & 0x400) != 0 )
    v3[6] = v4 | 0x10;
  *v3 = 72;
  *((_QWORD *)v3 + 1) = *(_QWORD *)(*a1 + 248);
  *((_QWORD *)v3 + 2) = a1[3];
  *((_QWORD *)v3 + 4) = (char *)a1 + 1996;
  *((_QWORD *)v3 + 5) = a1[258];
  v5 = a1[1];
  *((_DWORD *)a1 + 683) = 1;
  if ( (*(_DWORD *)(v5 + 204) & 0x800) != 0 )
  {
    *((_DWORD *)a1 + 683) = 4;
    v3[6] |= 0x80u;
  }
  if ( (unsigned int)HUBMISC_CheckIfU2ShouldBeSetForEnumeratedDevice(a1) == 4089 )
    v7 = *((unsigned __int16 *)a1 + 1106);
  else
    v7 = 0;
  v3[12] = v7;
  if ( (a1[205] & 2) != 0 )
    *((_BYTE *)v3 + 52) = 1;
  HUBUCX_ComputeUsb20HardwareLpmParameters(v6, v3);
  if ( (*((_DWORD *)a1 + 618) & 0x80u) != 0 && (a1[205] & 0x22) == 0x20 && *(_DWORD *)(a1[1] + 208) == 512 )
  {
    v3[6] |= 0x40u;
    if ( *(_BYTE *)(*a1 + 240) )
      *((_WORD *)v3 + 32) = 20;
    else
      *((_WORD *)v3 + 32) = *(unsigned __int8 *)(a1[314] + 5);
  }
  result = HUBUCX_SubmitUcxIoctl(a1, 0x491023u);
  if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = result;
    LOBYTE(v9) = 2;
    return WPP_RECORDER_SF_d(
             *(_QWORD *)(a1[1] + 1432),
             v9,
             5,
             33,
             (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
             v10);
  }
  return result;
}

```

## disassembly

```asm
0x140029104  mov     [rsp+arg_0], rbx
0x140029109  mov     [rsp+arg_8], rsi
0x14002910e  push    rdi
0x14002910f  sub     rsp, 30h
0x140029113  mov     rax, cs:WdfFunctions_01015
0x14002911a  mov     rdi, rcx
0x14002911d  mov     rbx, [rcx]
0x140029120  xor     r8d, r8d
0x140029123  mov     rdx, [rcx+1B8h]
0x14002912a  mov     rcx, cs:WdfDriverGlobals
0x140029131  mov     rax, [rax+610h]
0x140029138  call    _guard_dispatch_icall
0x14002913d  xor     edx, edx; Val
0x14002913f  mov     rcx, rax; void *
0x140029142  mov     rsi, rax
0x140029145  lea     r8d, [rdx+48h]; Size
0x140029149  call    memset
0x14002914e  or      dword ptr [rsi+18h], 0Bh
0x140029152  mov     r8d, [rsi+18h]
0x140029156  mov     ecx, r8d
0x140029159  or      ecx, 4
0x14002915c  and     r8d, 0FFFFFFFBh
0x140029160  test    byte ptr [rbx+9D0h], 4
0x140029167  cmovz   r8d, ecx
0x14002916b  mov     [rsi+18h], r8d
0x14002916f  test    dword ptr [rdi+674h], 400h
0x140029179  jz      short loc_140029183
0x14002917b  or      r8d, 10h
0x14002917f  mov     [rsi+18h], r8d
0x140029183  mov     dword ptr [rsi], 48h ; 'H'
0x140029189  mov     rax, [rdi]
0x14002918c  mov     rcx, [rax+0F8h]
0x140029193  mov     [rsi+8], rcx
0x140029197  mov     rax, [rdi+18h]
0x14002919b  mov     [rsi+10h], rax
0x14002919f  lea     rax, [rdi+7CCh]
0x1400291a6  mov     [rsi+20h], rax
0x1400291aa  mov     rax, [rdi+810h]
0x1400291b1  mov     [rsi+28h], rax
0x1400291b5  mov     rax, [rdi+8]
0x1400291b9  mov     dword ptr [rdi+0AACh], 1
0x1400291c3  test    dword ptr [rax+0CCh], 800h
0x1400291cd  jz      short loc_1400291DE
0x1400291cf  mov     dword ptr [rdi+0AACh], 4
0x1400291d9  bts     dword ptr [rsi+18h], 7
0x1400291de  mov     rcx, rdi
0x1400291e1  call    HUBMISC_CheckIfU2ShouldBeSetForEnumeratedDevice
0x1400291e6  cmp     eax, 0FF9h
0x1400291eb  jnz     short loc_1400291F6
0x1400291ed  movzx   eax, word ptr [rdi+8A4h]
0x1400291f4  jmp     short loc_1400291F8
0x1400291f6  xor     eax, eax
0x1400291f8  mov     [rsi+30h], eax
0x1400291fb  mov     eax, [rdi+668h]
0x140029201  test    al, 2
0x140029203  jz      short loc_140029209
0x140029205  mov     byte ptr [rsi+34h], 1
0x140029209  mov     rdx, rsi
0x14002920c  call    HUBUCX_ComputeUsb20HardwareLpmParameters
0x140029211  mov     eax, [rdi+9A8h]
0x140029217  test    al, al
0x140029219  jns     short loc_14002925E
0x14002921b  mov     eax, [rdi+668h]
0x140029221  and     al, 22h
0x140029223  cmp     al, 20h ; ' '
0x140029225  jnz     short loc_14002925E
0x140029227  mov     rax, [rdi+8]
0x14002922b  cmp     dword ptr [rax+0D0h], 200h
0x140029235  jnz     short loc_14002925E
0x140029237  or      dword ptr [rsi+18h], 40h
0x14002923b  mov     rax, [rdi]
0x14002923e  cmp     byte ptr [rax+0F0h], 0
0x140029245  jnz     short loc_140029258
0x140029247  mov     rax, [rdi+9D0h]
0x14002924e  movzx   ecx, byte ptr [rax+5]
0x140029252  mov     [rsi+40h], cx
0x140029256  jmp     short loc_14002925E
0x140029258  mov     word ptr [rsi+40h], 14h
0x14002925e  mov     edx, 491023h
0x140029263  mov     rcx, rdi
0x140029266  call    HUBUCX_SubmitUcxIoctl
0x14002926b  test    eax, eax
0x14002926d  jns     short loc_1400292AB
0x14002926f  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029276  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002927d  jz      short loc_1400292AB
0x14002927f  mov     rcx, [rdi+8]
0x140029283  mov     r9d, 21h ; '!'
0x140029289  mov     [rsp+38h+var_10], eax
0x14002928d  mov     dl, 2
0x14002928f  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140029296  mov     [rsp+38h+var_18], rax
0x14002929b  mov     rcx, [rcx+598h]
0x1400292a2  lea     r8d, [r9-1Ch]
0x1400292a6  call    WPP_RECORDER_SF_d
0x1400292ab  mov     rbx, [rsp+38h+arg_0]
0x1400292b0  mov     rsi, [rsp+38h+arg_8]
0x1400292b5  add     rsp, 30h
0x1400292b9  pop     rdi
0x1400292ba  retn
```
