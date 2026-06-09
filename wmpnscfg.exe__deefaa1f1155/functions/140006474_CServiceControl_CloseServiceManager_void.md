# CServiceControl::CloseServiceManager(void)

- ea: `0x140006474`
- end: `0x1400065c4`
- name: `?CloseServiceManager@CServiceControl@@AEAAXXZ`
- size: `336`
- prototype: `void __fastcall(CServiceControl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400063d4`
- `0x1400065cc`

## callees

- `0x1400053b4`
- `0x140006474`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1400064f5`
- `ADVAPI32!CloseServiceHandle` at `0x140006562`
- `ADVAPI32!CloseServiceHandle` at `0x1400064f5`
- `ADVAPI32!CloseServiceHandle` at `0x140006562`

## pseudocode

```c
void __fastcall CServiceControl::CloseServiceManager(CServiceControl *this)
{
  _QWORD *v2; // rcx
  SC_HANDLE v3; // rcx
  SC_HANDLE v4; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    {
      WPP_SF_(v2[2], 59, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)this + 2) )
  {
    v3 = (SC_HANDLE)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    CloseServiceHandle(v3);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_(v2[2], 61, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( *((_QWORD *)this + 1) )
  {
    v4 = (SC_HANDLE)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = 0;
    CloseServiceHandle(v4);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_(v2[2], 67, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
}

```

## disassembly

```asm
0x140006474  mov     [rsp+arg_0], rbx
0x140006479  mov     [rsp+arg_8], rsi
0x14000647e  push    rdi
0x14000647f  sub     rsp, 20h
0x140006483  mov     rbx, rcx
0x140006486  mov     rcx, cs:WPP_GLOBAL_Control
0x14000648d  lea     rdi, WPP_GLOBAL_Control
0x140006494  lea     rsi, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000649b  cmp     rcx, rdi
0x14000649e  jz      short loc_1400064E1
0x1400064a0  test    byte ptr [rcx+1Ch], 1
0x1400064a4  jz      short loc_1400064BE
0x1400064a6  mov     rcx, [rcx+10h]
0x1400064aa  mov     edx, 41h ; 'A'
0x1400064af  mov     r8, rsi
0x1400064b2  call    WPP_SF_
0x1400064b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064be  cmp     rcx, rdi
0x1400064c1  jz      short loc_1400064E1
0x1400064c3  test    byte ptr [rcx+1Ch], 1
0x1400064c7  jz      short loc_1400064E1
0x1400064c9  mov     rcx, [rcx+10h]
0x1400064cd  mov     edx, 3Bh ; ';'
0x1400064d2  mov     r8, rsi
0x1400064d5  call    WPP_SF_
0x1400064da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064e1  mov     rax, [rbx+10h]
0x1400064e5  test    rax, rax
0x1400064e8  jz      short loc_14000652B
0x1400064ea  mov     rcx, rax; hSCObject
0x1400064ed  mov     qword ptr [rbx+10h], 0
0x1400064f5  call    cs:__imp_CloseServiceHandle
0x1400064fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140006502  cmp     rcx, rdi
0x140006505  jz      short loc_14000654E
0x140006507  test    byte ptr [rcx+1Ch], 2
0x14000650b  jz      short loc_14000652B
0x14000650d  cmp     byte ptr [rcx+19h], 4
0x140006511  jb      short loc_14000652B
0x140006513  mov     rcx, [rcx+10h]
0x140006517  mov     edx, 3Ch ; '<'
0x14000651c  mov     r8, rsi
0x14000651f  call    WPP_SF_
0x140006524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000652b  cmp     rcx, rdi
0x14000652e  jz      short loc_14000654E
0x140006530  test    byte ptr [rcx+1Ch], 1
0x140006534  jz      short loc_14000654E
0x140006536  mov     rcx, [rcx+10h]
0x14000653a  mov     edx, 3Dh ; '='
0x14000653f  mov     r8, rsi
0x140006542  call    WPP_SF_
0x140006547  mov     rcx, cs:WPP_GLOBAL_Control
0x14000654e  mov     rax, [rbx+8]
0x140006552  test    rax, rax
0x140006555  jz      short loc_140006598
0x140006557  mov     rcx, rax; hSCObject
0x14000655a  mov     qword ptr [rbx+8], 0
0x140006562  call    cs:__imp_CloseServiceHandle
0x140006568  mov     rcx, cs:WPP_GLOBAL_Control
0x14000656f  cmp     rcx, rdi
0x140006572  jz      short loc_1400065B4
0x140006574  test    byte ptr [rcx+1Ch], 2
0x140006578  jz      short loc_140006598
0x14000657a  cmp     byte ptr [rcx+19h], 4
0x14000657e  jb      short loc_140006598
0x140006580  mov     rcx, [rcx+10h]
0x140006584  mov     edx, 42h ; 'B'
0x140006589  mov     r8, rsi
0x14000658c  call    WPP_SF_
0x140006591  mov     rcx, cs:WPP_GLOBAL_Control
0x140006598  cmp     rcx, rdi
0x14000659b  jz      short loc_1400065B4
0x14000659d  test    byte ptr [rcx+1Ch], 1
0x1400065a1  jz      short loc_1400065B4
0x1400065a3  mov     rcx, [rcx+10h]
0x1400065a7  mov     edx, 43h ; 'C'
0x1400065ac  mov     r8, rsi
0x1400065af  call    WPP_SF_
0x1400065b4  mov     rbx, [rsp+28h+arg_0]
0x1400065b9  mov     rsi, [rsp+28h+arg_8]
0x1400065be  add     rsp, 20h
0x1400065c2  pop     rdi
0x1400065c3  retn
```
