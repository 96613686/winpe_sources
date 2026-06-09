# DllCanUnloadNow

- ea: `0x1800032e0`
- end: `0x18000335a`
- name: `DllCanUnloadNow`
- size: `122`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800032e0`
- `0x180003860`
- `0x180003888`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  _QWORD *v0; // rcx
  _BOOL8 v1; // rbx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  v1 = g_cLocks != 0;
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_d(v0[2], 13, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids, g_cLocks != 0);
  return v1;
}

```

## disassembly

```asm
0x1800032e0  mov     [rsp+arg_0], rbx
0x1800032e5  push    rdi
0x1800032e6  sub     rsp, 20h
0x1800032ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032f1  lea     rdi, WPP_GLOBAL_Control
0x1800032f8  cmp     rcx, rdi
0x1800032fb  jz      short loc_18000331F
0x1800032fd  test    byte ptr [rcx+1Ch], 20h
0x180003301  jz      short loc_18000331F
0x180003303  mov     rcx, [rcx+10h]
0x180003307  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x18000330e  mov     edx, 0Ch
0x180003313  call    WPP_SF_
0x180003318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000331f  xor     ebx, ebx
0x180003321  cmp     cs:?g_cLocks@@3JA, ebx; long g_cLocks
0x180003327  setnz   bl
0x18000332a  cmp     rcx, rdi
0x18000332d  jz      short loc_18000334D
0x18000332f  test    byte ptr [rcx+1Ch], 20h
0x180003333  jz      short loc_18000334D
0x180003335  mov     rcx, [rcx+10h]
0x180003339  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x180003340  mov     edx, 0Dh
0x180003345  mov     r9d, ebx
0x180003348  call    WPP_SF_d
0x18000334d  mov     eax, ebx
0x18000334f  mov     rbx, [rsp+28h+arg_0]
0x180003354  add     rsp, 20h
0x180003358  pop     rdi
0x180003359  retn
```
