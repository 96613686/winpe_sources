# CDeviceSettings::GetAuthorizationStatus(AuthorizationStatus *)

- ea: `0x180004358`
- end: `0x1800043dd`
- name: `?GetAuthorizationStatus@CDeviceSettings@@QEAAJPEAW4AuthorizationStatus@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CDeviceSettings *__hidden this, enum AuthorizationStatus *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008e84`
- `0x180009030`
- `0x18000e4b0`
- `0x1800119e0`
- `0x180011c20`
- `0x180011e10`
- `0x180011f80`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004358`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::GetAuthorizationStatus(CDeviceSettings *this, enum AuthorizationStatus *a2)
{
  _UNKNOWN **v4; // rcx
  unsigned int v5; // ebx

  v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x30u, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = 0;
    *(_DWORD *)a2 = *((_DWORD *)this + 20);
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d((TRACEHANDLE)v4[2], 0x31u, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180004358  push    rbx
0x18000435a  push    rbp
0x18000435b  push    rsi
0x18000435c  push    rdi
0x18000435d  sub     rsp, 28h
0x180004361  mov     rdi, rdx
0x180004364  mov     rsi, rcx
0x180004367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000436e  lea     rbp, WPP_GLOBAL_Control
0x180004375  cmp     rcx, rbp
0x180004378  jz      short loc_18000439C
0x18000437a  test    byte ptr [rcx+1Ch], 20h
0x18000437e  jz      short loc_18000439C
0x180004380  mov     rcx, [rcx+10h]
0x180004384  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000438b  mov     edx, 30h ; '0'
0x180004390  call    WPP_SF_
0x180004395  mov     rcx, cs:WPP_GLOBAL_Control
0x18000439c  test    rdi, rdi
0x18000439f  jz      short loc_1800043AA
0x1800043a1  mov     eax, [rsi+50h]
0x1800043a4  xor     ebx, ebx
0x1800043a6  mov     [rdi], eax
0x1800043a8  jmp     short loc_1800043AF
0x1800043aa  mov     ebx, 80004003h
0x1800043af  cmp     rcx, rbp
0x1800043b2  jz      short loc_1800043D2
0x1800043b4  test    byte ptr [rcx+1Ch], 20h
0x1800043b8  jz      short loc_1800043D2
0x1800043ba  mov     rcx, [rcx+10h]
0x1800043be  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800043c5  mov     edx, 31h ; '1'
0x1800043ca  mov     r9d, ebx
0x1800043cd  call    WPP_SF_d
0x1800043d2  mov     eax, ebx
0x1800043d4  add     rsp, 28h
0x1800043d8  pop     rdi
0x1800043d9  pop     rsi
0x1800043da  pop     rbp
0x1800043db  pop     rbx
0x1800043dc  retn
```
