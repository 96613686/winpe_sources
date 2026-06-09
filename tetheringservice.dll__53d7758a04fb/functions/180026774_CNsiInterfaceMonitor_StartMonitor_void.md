# CNsiInterfaceMonitor::StartMonitor(void)

- ea: `0x180026774`
- end: `0x180026927`
- name: `?StartMonitor@CNsiInterfaceMonitor@@QEAAKXZ`
- size: `435`
- prototype: `__int64 __fastcall(CNsiInterfaceMonitor *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001e4a4`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x180026774`

## import_xrefs

- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180026843`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180026843`
- `WINNSI!NsiDisconnectFromServer` at `0x180026896`
- `WINNSI!NsiDisconnectFromServer` at `0x180026896`
- `WINNSI!NsiConnectToServer` at `0x1800267e6`
- `WINNSI!NsiConnectToServer` at `0x1800267e6`

## pseudocode

```c
__int64 __fastcall CNsiInterfaceMonitor::StartMonitor(CNsiInterfaceMonitor *this)
{
  TetheringServiceTelemetry *v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    v4 = 1247;
    if ( v2 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)v2 + 28) & 8) == 0 )
      goto LABEL_29;
    v6 = 16;
    goto LABEL_27;
  }
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v2 + 2), 11, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
  v3 = NsiConnectToServer(0);
  *((_QWORD *)this + 2) = v3;
  if ( !v3 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v4 = 6;
    goto LABEL_29;
  }
  v4 = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
  }
  v5 = NsiRpcRegisterChangeNotification(
         *((_QWORD *)this + 2),
         &NPI_MS_NDIS_MODULEID,
         1,
         &CNsiInterfaceMonitor::NsiChangeCallback,
         1,
         this,
         (char *)this + 24);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_25f318119957394f188ed969a8444d7a_Traceguids, v5);
    }
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    goto LABEL_28;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v6 = 13;
LABEL_27:
    WPP_SF_(*((_QWORD *)v2 + 2), v6, &WPP_25f318119957394f188ed969a8444d7a_Traceguids);
LABEL_28:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 17, &WPP_25f318119957394f188ed969a8444d7a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180026774  push    rbx
0x180026776  push    rbp
0x180026777  push    rsi
0x180026778  push    rdi
0x180026779  push    r14
0x18002677b  sub     rsp, 40h
0x18002677f  mov     rdi, rcx
0x180026782  mov     rcx, cs:WPP_GLOBAL_Control
0x180026789  lea     rbp, WPP_GLOBAL_Control
0x180026790  lea     r14, WPP_25f318119957394f188ed969a8444d7a_Traceguids
0x180026797  cmp     rcx, rbp
0x18002679a  jz      short loc_1800267BA
0x18002679c  test    byte ptr [rcx+1Ch], 8
0x1800267a0  jz      short loc_1800267BA
0x1800267a2  mov     rcx, [rcx+10h]
0x1800267a6  mov     edx, 0Ah
0x1800267ab  mov     r8, r14
0x1800267ae  call    WPP_SF_
0x1800267b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267ba  lea     rsi, [rdi+18h]
0x1800267be  cmp     qword ptr [rsi], 0
0x1800267c2  jnz     loc_1800268D3
0x1800267c8  cmp     rcx, rbp
0x1800267cb  jz      short loc_1800267E4
0x1800267cd  test    byte ptr [rcx+1Ch], 8
0x1800267d1  jz      short loc_1800267E4
0x1800267d3  mov     rcx, [rcx+10h]
0x1800267d7  mov     edx, 0Bh
0x1800267dc  mov     r8, r14
0x1800267df  call    WPP_SF_
0x1800267e4  xor     ecx, ecx
0x1800267e6  call    cs:__imp_NsiConnectToServer
0x1800267ec  mov     [rdi+10h], rax
0x1800267f0  test    rax, rax
0x1800267f3  jz      loc_1800268A2
0x1800267f9  xor     ebx, ebx
0x1800267fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180026802  cmp     rcx, rbp
0x180026805  jz      short loc_18002681C
0x180026807  test    byte ptr [rcx+1Ch], 8
0x18002680b  jz      short loc_18002681C
0x18002680d  mov     rcx, [rcx+10h]
0x180026811  lea     edx, [rbx+0Ch]
0x180026814  mov     r8, r14
0x180026817  call    WPP_SF_
0x18002681c  mov     rcx, [rdi+10h]
0x180026820  lea     r9, ?NsiChangeCallback@CNsiInterfaceMonitor@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z; CNsiInterfaceMonitor::NsiChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)
0x180026827  mov     [rsp+68h+var_38], rsi
0x18002682c  lea     rdx, NPI_MS_NDIS_MODULEID
0x180026833  mov     [rsp+68h+var_40], rdi
0x180026838  mov     r8d, 1
0x18002683e  mov     [rsp+68h+var_48], 1
0x180026843  call    cs:__imp_NsiRpcRegisterChangeNotification
0x180026849  test    eax, eax
0x18002684b  jnz     short loc_18002686C
0x18002684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026854  cmp     rcx, rbp
0x180026857  jz      loc_18002691A
0x18002685d  test    byte ptr [rcx+1Ch], 8
0x180026861  jz      loc_1800268FB
0x180026867  lea     edx, [rax+0Dh]
0x18002686a  jmp     short loc_1800268E8
0x18002686c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026873  cmp     rcx, rbp
0x180026876  jz      short loc_180026892
0x180026878  test    byte ptr [rcx+1Ch], 1
0x18002687c  jz      short loc_180026892
0x18002687e  mov     rcx, [rcx+10h]
0x180026882  mov     edx, 0Eh
0x180026887  mov     r9d, eax
0x18002688a  mov     r8, r14
0x18002688d  call    WPP_SF_d
0x180026892  mov     rcx, [rdi+10h]
0x180026896  call    cs:__imp_NsiDisconnectFromServer
0x18002689c  mov     [rdi+10h], rbx
0x1800268a0  jmp     short loc_1800268F4
0x1800268a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268a9  cmp     rcx, rbp
0x1800268ac  jz      short loc_1800268CC
0x1800268ae  test    byte ptr [rcx+1Ch], 1
0x1800268b2  jz      short loc_1800268CC
0x1800268b4  mov     rcx, [rcx+10h]
0x1800268b8  mov     edx, 0Fh
0x1800268bd  mov     r8, r14
0x1800268c0  call    WPP_SF_
0x1800268c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268cc  mov     ebx, 6
0x1800268d1  jmp     short loc_1800268FB
0x1800268d3  mov     ebx, 4DFh
0x1800268d8  cmp     rcx, rbp
0x1800268db  jz      short loc_18002691A
0x1800268dd  test    byte ptr [rcx+1Ch], 8
0x1800268e1  jz      short loc_1800268FB
0x1800268e3  mov     edx, 10h
0x1800268e8  mov     rcx, [rcx+10h]
0x1800268ec  mov     r8, r14
0x1800268ef  call    WPP_SF_
0x1800268f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268fb  cmp     rcx, rbp
0x1800268fe  jz      short loc_18002691A
0x180026900  test    byte ptr [rcx+1Ch], 8
0x180026904  jz      short loc_18002691A
0x180026906  mov     rcx, [rcx+10h]
0x18002690a  mov     edx, 11h
0x18002690f  mov     r9d, ebx
0x180026912  mov     r8, r14
0x180026915  call    WPP_SF_d
0x18002691a  mov     eax, ebx
0x18002691c  add     rsp, 40h
0x180026920  pop     r14
0x180026922  pop     rdi
0x180026923  pop     rsi
0x180026924  pop     rbp
0x180026925  pop     rbx
0x180026926  retn
```
