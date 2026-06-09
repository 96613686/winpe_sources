# HUBUCX_DisableAllEndpointsForCurrentConfigurationUsingUCXIoctl

- ea: `0x140026620`
- end: `0x140026736`
- name: `HUBUCX_DisableAllEndpointsForCurrentConfigurationUsingUCXIoctl`
- size: `278`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400210f0`
- `0x140021690`
- `0x1400216c0`

## callees

- `0x1400067ac`
- `0x14000a53c`
- `0x140026620`
- `0x14002692c`

## pseudocode

```c
__int64 __fastcall HUBUCX_DisableAllEndpointsForCurrentConfigurationUsingUCXIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  _QWORD *v5; // r10
  _QWORD *i; // rax
  unsigned int j; // r9d
  int v8; // ecx
  _QWORD *v9; // r8

  v2 = *(_QWORD *)(a1 + 48);
  if ( !v2 )
    return HUBSM_AddEvent(a1 + 512, 4028);
  if ( !*(_DWORD *)(a1 + 96) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        a2,
        5,
        57,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids);
    }
    return HUBSM_AddEvent(a1 + 512, 4028);
  }
  v5 = (_QWORD *)(v2 + 16);
  *(_DWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  for ( i = *(_QWORD **)(v2 + 16); ; i = (_QWORD *)*i )
  {
    v9 = i - 1;
    if ( v5 == i )
      break;
    for ( j = 0; j < *((_DWORD *)v9 + 6); ++j )
    {
      v8 = v9[10 * j + 6];
      if ( v8 == 4 )
      {
        LODWORD(v9[10 * j + 6]) = 5;
        a2 = *(unsigned int *)(a1 + 128);
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8 * a2) = v9[10 * j + 5];
        ++*(_DWORD *)(a1 + 128);
      }
      else if ( v8 == 6 )
      {
        a2 = *(unsigned int *)(a1 + 144);
        *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * a2) = v9[10 * j + 5];
        ++*(_DWORD *)(a1 + 144);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 128) )
    return HUBSM_AddEvent(a1 + 512, 4028);
  return HUBUCX_EnableDisableEndpointsUsingUCXIoctl(a1, a2, v9);
}

```

## disassembly

```asm
0x140026620  push    rbx
0x140026622  sub     rsp, 30h
0x140026626  mov     rax, [rcx+30h]
0x14002662a  xor     r11d, r11d
0x14002662d  mov     rbx, rcx
0x140026630  test    rax, rax
0x140026633  jz      short loc_140026671
0x140026635  cmp     [rcx+60h], r11d
0x140026639  jnz     short loc_140026689
0x14002663b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026642  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026649  jz      short loc_140026671
0x14002664b  mov     rcx, [rcx+8]
0x14002664f  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140026656  lea     r9d, [r11+39h]
0x14002665a  mov     [rsp+38h+var_18], rax
0x14002665f  lea     r8d, [r11+5]
0x140026663  mov     dl, 4
0x140026665  mov     rcx, [rcx+598h]
0x14002666c  call    WPP_RECORDER_SF_
0x140026671  lea     rcx, [rbx+200h]
0x140026678  mov     edx, 0FBCh
0x14002667d  call    HUBSM_AddEvent
0x140026682  add     rsp, 30h
0x140026686  pop     rbx
0x140026687  retn
0x140026689  lea     r10, [rax+10h]
0x14002668d  mov     [rcx+70h], r11d
0x140026691  mov     [rcx+90h], r11d
0x140026698  mov     [rcx+80h], r11d
0x14002669f  mov     rax, [r10]
0x1400266a2  jmp     short loc_140026713
0x1400266a4  mov     r9d, r11d
0x1400266a7  cmp     [r8+18h], r11d
0x1400266ab  jbe     short loc_14002670F
0x1400266ad  mov     eax, r9d
0x1400266b0  lea     rax, [rax+rax*4]
0x1400266b4  add     rax, rax
0x1400266b7  mov     ecx, [r8+rax*8+30h]
0x1400266bc  cmp     ecx, 4
0x1400266bf  jz      short loc_1400266E4
0x1400266c1  cmp     ecx, 6
0x1400266c4  jnz     short loc_140026706
0x1400266c6  mov     edx, [rbx+90h]
0x1400266cc  mov     rax, [r8+rax*8+28h]
0x1400266d1  mov     rcx, [rbx+88h]
0x1400266d8  mov     [rcx+rdx*8], rax
0x1400266dc  inc     dword ptr [rbx+90h]
0x1400266e2  jmp     short loc_140026706
0x1400266e4  mov     dword ptr [r8+rax*8+30h], 5
0x1400266ed  mov     edx, [rbx+80h]
0x1400266f3  mov     rax, [r8+rax*8+28h]
0x1400266f8  mov     rcx, [rbx+78h]
0x1400266fc  mov     [rcx+rdx*8], rax
0x140026700  inc     dword ptr [rbx+80h]
0x140026706  inc     r9d
0x140026709  cmp     r9d, [r8+18h]
0x14002670d  jb      short loc_1400266AD
0x14002670f  mov     rax, [r8+8]
0x140026713  lea     r8, [rax-8]
0x140026717  cmp     r10, rax
0x14002671a  jnz     short loc_1400266A4
0x14002671c  cmp     [rbx+80h], r11d
0x140026723  jz      loc_140026671
0x140026729  mov     rcx, rbx
0x14002672c  call    HUBUCX_EnableDisableEndpointsUsingUCXIoctl
0x140026731  jmp     loc_140026682
```
