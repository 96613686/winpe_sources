# MSMSecInitialize

- ea: `0x1800532c0`
- end: `0x1800533e0`
- name: `MSMSecInitialize`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x180050770`
- `0x1800532c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180053399`
- `MobileNetworking!ReleaseWriteLock` at `0x180053399`
- `MobileNetworking!AcquireWriteLock` at `0x180053316`
- `MobileNetworking!AcquireWriteLock` at `0x180053316`

## pseudocode

```c
__int64 MSMSecInitialize()
{
  int v0; // edx
  const char *v1; // rcx
  unsigned int v2; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  AcquireWriteLock(&g_MSMSecState, qword_1800AEF28, "MSMSecInitialize", 19);
  v1 = (const char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v2 = IncrementMSMSecRefCountEx(v1, v0);
  v3 = v2;
  if ( v2 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v2);
  ReleaseWriteLock(&g_MSMSecState, qword_1800AEF28, "MSMSecInitialize", 27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800532c0  mov     [rsp+arg_0], rbx
0x1800532c5  push    rsi
0x1800532c6  sub     rsp, 20h
0x1800532ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800532d1  lea     rsi, WPP_GLOBAL_Control
0x1800532d8  cmp     rcx, rsi
0x1800532db  jz      short loc_1800532FB
0x1800532dd  test    dword ptr [rcx+44h], 100h
0x1800532e4  jz      short loc_1800532FB
0x1800532e6  mov     rcx, [rcx+38h]
0x1800532ea  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800532f1  mov     edx, 0Ah
0x1800532f6  call    WPP_SF_
0x1800532fb  mov     r9d, 13h
0x180053301  lea     r8, aMsmsecinitiali_2; "MSMSecInitialize"
0x180053308  lea     rdx, qword_1800AEF28
0x18005330f  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180053316  call    cs:__imp_AcquireWriteLock
0x18005331d  nop     dword ptr [rax+rax+00h]
0x180053322  mov     rcx, cs:WPP_GLOBAL_Control
0x180053329  cmp     rcx, rsi
0x18005332c  jz      short loc_180053349
0x18005332e  test    byte ptr [rcx+44h], 20h
0x180053332  jz      short loc_180053349
0x180053334  mov     rcx, [rcx+38h]
0x180053338  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18005333f  mov     edx, 0Bh
0x180053344  call    WPP_SF_
0x180053349  call    ?IncrementMSMSecRefCountEx@@YAKPEBDH@Z; IncrementMSMSecRefCountEx(char const *,int)
0x18005334e  mov     ebx, eax
0x180053350  test    eax, eax
0x180053352  jz      short loc_18005337E
0x180053354  mov     rcx, cs:WPP_GLOBAL_Control
0x18005335b  cmp     rcx, rsi
0x18005335e  jz      short loc_18005337E
0x180053360  test    byte ptr [rcx+44h], 1
0x180053364  jz      short loc_18005337E
0x180053366  mov     rcx, [rcx+38h]
0x18005336a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053371  mov     edx, 0Ch
0x180053376  mov     r9d, eax
0x180053379  call    WPP_SF_d
0x18005337e  mov     r9d, 1Bh
0x180053384  lea     r8, aMsmsecinitiali_2; "MSMSecInitialize"
0x18005338b  lea     rdx, qword_1800AEF28
0x180053392  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180053399  call    cs:__imp_ReleaseWriteLock
0x1800533a0  nop     dword ptr [rax+rax+00h]
0x1800533a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800533ac  cmp     rcx, rsi
0x1800533af  jz      short loc_1800533D2
0x1800533b1  test    dword ptr [rcx+44h], 100h
0x1800533b8  jz      short loc_1800533D2
0x1800533ba  mov     rcx, [rcx+38h]
0x1800533be  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800533c5  mov     edx, 0Dh
0x1800533ca  mov     r9d, ebx
0x1800533cd  call    WPP_SF_d
0x1800533d2  mov     eax, ebx
0x1800533d4  mov     rbx, [rsp+28h+arg_0]
0x1800533d9  add     rsp, 20h
0x1800533dd  pop     rsi
0x1800533de  retn
```
