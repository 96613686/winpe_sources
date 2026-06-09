# StopService(SC_HANDLE__ *,SC_HANDLE__ *,ulong)

- ea: `0x140049898`
- end: `0x140049aa0`
- name: `?StopService@@YAKPEAUSC_HANDLE__@@0K@Z`
- size: `520`
- prototype: `unsigned int(struct SC_HANDLE__ *, struct SC_HANDLE__ *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140049b50`

## callees

- `0x14003f17c`
- `0x140045f20`
- `0x140047798`
- `0x140049898`
- `0x14004a240`
- `0x14004a964`

## import_xrefs

- `ADVAPI32!QueryServiceStatusEx` at `0x140049923`
- `ADVAPI32!QueryServiceStatusEx` at `0x140049923`
- `ADVAPI32!ControlService` at `0x140049a87`
- `ADVAPI32!ControlService` at `0x140049a87`
- `KERNEL32!GetTickCount` at `0x1400498f9`
- `KERNEL32!GetTickCount` at `0x1400498f9`
- `KERNEL32!GetLastError` at `0x140049934`
- `KERNEL32!GetLastError` at `0x140049a95`
- `KERNEL32!GetLastError` at `0x140049934`
- `KERNEL32!GetLastError` at `0x140049a95`

## pseudocode

```c
__int64 __fastcall StopService(struct SC_HANDLE__ *a1, SC_HANDLE a2, __int64 a3)
{
  DWORD TickCount; // edi
  unsigned int v5; // r9d
  DWORD v6; // eax
  DWORD v7; // ebx
  PVOID *v8; // r10
  DWORD LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-58h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+48h] [rbp-40h]
  int v14; // [rsp+58h] [rbp-30h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2);
  }
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  v13 = 0;
  pcbBytesNeeded = 0;
  TickCount = GetTickCount();
  if ( QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    if ( *(_DWORD *)&Buffer[4] == 1 )
    {
      v7 = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_23;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      goto LABEL_22;
    }
    if ( *(_DWORD *)&Buffer[4] == 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
      if ( !ControlService(a2, 1u, (LPSERVICE_STATUS)Buffer) )
      {
        LastError = GetLastError();
        goto LABEL_21;
      }
    }
    LastError = WaitForStop(a2, Buffer, TickCount, v5);
LABEL_21:
    v7 = LastError;
    goto LABEL_22;
  }
  v6 = GetLastError();
  v7 = v6;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v6);
LABEL_22:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v8 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v8 + 28) & 1) != 0
    && *((unsigned __int8 *)v8 + 25) >= (unsigned int)(v7 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v8[2], 62, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140049898  mov     [rsp+arg_10], rbx
0x14004989d  push    rbp
0x14004989e  push    rsi
0x14004989f  push    rdi
0x1400498a0  sub     rsp, 70h
0x1400498a4  mov     rax, cs:__security_cookie
0x1400498ab  xor     rax, rsp
0x1400498ae  mov     [rsp+88h+var_28], rax
0x1400498b3  mov     rbx, rdx
0x1400498b6  mov     r9, rcx
0x1400498b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498c0  lea     rsi, WPP_GLOBAL_Control
0x1400498c7  cmp     rcx, rsi
0x1400498ca  jz      short loc_1400498E6
0x1400498cc  test    byte ptr [rcx+1Ch], 1
0x1400498d0  jz      short loc_1400498E6
0x1400498d2  cmp     byte ptr [rcx+19h], 5
0x1400498d6  jb      short loc_1400498E6
0x1400498d8  mov     rcx, [rcx+10h]
0x1400498dc  mov     [rsp+88h+pcbBytesNeeded], rdx
0x1400498e1  call    WPP_SF_qqD
0x1400498e6  xorps   xmm0, xmm0
0x1400498e9  xor     eax, eax
0x1400498eb  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x1400498f0  mov     [rsp+88h+var_30], eax
0x1400498f4  movups  [rsp+88h+var_40], xmm0
0x1400498f9  call    cs:__imp_GetTickCount
0x1400498ff  mov     r9d, 24h ; '$'; cbBufSize
0x140049905  mov     [rsp+88h+var_58], 0
0x14004990d  mov     edi, eax
0x14004990f  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x140049914  lea     rax, [rsp+88h+var_58]
0x140049919  xor     edx, edx; InfoLevel
0x14004991b  mov     rcx, rbx; hService
0x14004991e  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140049923  call    cs:__imp_QueryServiceStatusEx
0x140049929  lea     rbp, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140049930  test    eax, eax
0x140049932  jnz     short loc_140049978
0x140049934  call    cs:__imp_GetLastError
0x14004993a  mov     ebx, eax
0x14004993c  mov     r10, cs:WPP_GLOBAL_Control
0x140049943  cmp     r10, rsi
0x140049946  jz      loc_140049A32
0x14004994c  test    byte ptr [r10+1Ch], 2
0x140049951  jz      loc_1400499FD
0x140049957  cmp     byte ptr [r10+19h], 2
0x14004995c  jb      loc_1400499FD
0x140049962  mov     rcx, [r10+10h]
0x140049966  mov     edx, 3Ah ; ':'
0x14004996b  mov     r9d, eax
0x14004996e  mov     r8, rbp
0x140049971  call    WPP_SF_d
0x140049976  jmp     short loc_1400499F6
0x140049978  cmp     dword ptr [rsp+88h+Buffer+4], 1
0x14004997d  jnz     short loc_1400499B0
0x14004997f  xor     ebx, ebx
0x140049981  mov     r10, cs:WPP_GLOBAL_Control
0x140049988  cmp     r10, rsi
0x14004998b  jz      loc_140049A32
0x140049991  test    byte ptr [r10+1Ch], 2
0x140049996  jz      short loc_1400499FD
0x140049998  cmp     byte ptr [r10+19h], 5
0x14004999d  jb      short loc_1400499FD
0x14004999f  mov     rcx, [r10+10h]
0x1400499a3  lea     edx, [rbx+3Bh]
0x1400499a6  mov     r8, rbp
0x1400499a9  call    WPP_SF_
0x1400499ae  jmp     short loc_1400499F6
0x1400499b0  cmp     dword ptr [rsp+88h+Buffer+4], 3
0x1400499b5  jnz     loc_140049A51
0x1400499bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499c2  cmp     rcx, rsi
0x1400499c5  jz      short loc_1400499E4
0x1400499c7  test    byte ptr [rcx+1Ch], 2
0x1400499cb  jz      short loc_1400499E4
0x1400499cd  cmp     byte ptr [rcx+19h], 5
0x1400499d1  jb      short loc_1400499E4
0x1400499d3  mov     rcx, [rcx+10h]
0x1400499d7  mov     edx, 3Ch ; '<'
0x1400499dc  mov     r8, rbp
0x1400499df  call    WPP_SF_
0x1400499e4  mov     r8d, edi; unsigned int
0x1400499e7  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x1400499ec  mov     rcx, rbx; hService
0x1400499ef  call    ?WaitForStop@@YAKPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@KK@Z; WaitForStop(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *,ulong,ulong)
0x1400499f4  mov     ebx, eax
0x1400499f6  mov     r10, cs:WPP_GLOBAL_Control
0x1400499fd  cmp     r10, rsi
0x140049a00  jz      short loc_140049A32
0x140049a02  test    byte ptr [r10+1Ch], 1
0x140049a07  jz      short loc_140049A32
0x140049a09  movzx   edx, byte ptr [r10+19h]
0x140049a0e  mov     eax, ebx
0x140049a10  neg     eax
0x140049a12  sbb     ecx, ecx
0x140049a14  and     ecx, 0FFFFFFFDh
0x140049a17  add     ecx, 5
0x140049a1a  cmp     edx, ecx
0x140049a1c  jb      short loc_140049A32
0x140049a1e  mov     rcx, [r10+10h]
0x140049a22  mov     edx, 3Eh ; '>'
0x140049a27  mov     r9d, ebx
0x140049a2a  mov     r8, rbp
0x140049a2d  call    WPP_SF_d
0x140049a32  mov     eax, ebx
0x140049a34  mov     rcx, [rsp+88h+var_28]
0x140049a39  xor     rcx, rsp; StackCookie
0x140049a3c  call    __security_check_cookie
0x140049a41  mov     rbx, [rsp+88h+arg_10]
0x140049a49  add     rsp, 70h
0x140049a4d  pop     rdi
0x140049a4e  pop     rsi
0x140049a4f  pop     rbp
0x140049a50  retn
0x140049a51  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a58  cmp     rcx, rsi
0x140049a5b  jz      short loc_140049A7A
0x140049a5d  test    byte ptr [rcx+1Ch], 2
0x140049a61  jz      short loc_140049A7A
0x140049a63  cmp     byte ptr [rcx+19h], 5
0x140049a67  jb      short loc_140049A7A
0x140049a69  mov     rcx, [rcx+10h]
0x140049a6d  mov     edx, 3Dh ; '='
0x140049a72  mov     r8, rbp
0x140049a75  call    WPP_SF_
0x140049a7a  lea     r8, [rsp+88h+Buffer]; lpServiceStatus
0x140049a7f  mov     edx, 1; dwControl
0x140049a84  mov     rcx, rbx; hService
0x140049a87  call    cs:__imp_ControlService
0x140049a8d  test    eax, eax
0x140049a8f  jnz     loc_1400499E4
0x140049a95  call    cs:__imp_GetLastError
0x140049a9b  jmp     loc_1400499F4
```
