# CServiceControl::OpenServiceManager(void)

- ea: `0x140091984`
- end: `0x140091a68`
- name: `?OpenServiceManager@CServiceControl@@AEAAHXZ`
- size: `228`
- prototype: `__int64 __fastcall(CServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140091a70`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x140091984`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1400919e1`
- `ADVAPI32!OpenSCManagerW` at `0x1400919e1`
- `KERNEL32!GetLastError` at `0x1400919f2`
- `KERNEL32!GetLastError` at `0x1400919f2`

## pseudocode

```c
__int64 __fastcall CServiceControl::OpenServiceManager(CServiceControl *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  DWORD LastError; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_cb23d491edf93b904e2862226171c496_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 1;
  if ( *((_QWORD *)this + 1) )
    goto LABEL_11;
  v4 = OpenSCManagerW(0, 0, 0x20001u);
  *((_QWORD *)this + 1) = v4;
  if ( v4 )
    goto LABEL_10;
  v3 = 0;
  LastError = GetLastError();
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_cb23d491edf93b904e2862226171c496_Traceguids, LastError);
LABEL_10:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(v2[2], 64, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x140091984  mov     [rsp+arg_0], rbx
0x140091989  mov     [rsp+arg_8], rsi
0x14009198e  push    rdi
0x14009198f  sub     rsp, 20h
0x140091993  mov     rdi, rcx
0x140091996  mov     rcx, cs:WPP_GLOBAL_Control
0x14009199d  lea     rsi, WPP_GLOBAL_Control
0x1400919a4  cmp     rcx, rsi
0x1400919a7  jz      short loc_1400919CB
0x1400919a9  test    byte ptr [rcx+1Ch], 1
0x1400919ad  jz      short loc_1400919CB
0x1400919af  mov     rcx, [rcx+10h]
0x1400919b3  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x1400919ba  mov     edx, 3Eh ; '>'
0x1400919bf  call    WPP_SF_
0x1400919c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400919cb  cmp     qword ptr [rdi+8], 0
0x1400919d0  mov     ebx, 1
0x1400919d5  jnz     short loc_140091A2D
0x1400919d7  xor     edx, edx; lpDatabaseName
0x1400919d9  mov     r8d, 20001h; dwDesiredAccess
0x1400919df  xor     ecx, ecx; lpMachineName
0x1400919e1  call    cs:__imp_OpenSCManagerW
0x1400919e7  mov     [rdi+8], rax
0x1400919eb  test    rax, rax
0x1400919ee  jnz     short loc_140091A26
0x1400919f0  xor     ebx, ebx
0x1400919f2  call    cs:__imp_GetLastError
0x1400919f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400919ff  cmp     rcx, rsi
0x140091a02  jz      short loc_140091A56
0x140091a04  test    byte ptr [rcx+1Ch], 2
0x140091a08  jz      short loc_140091A2D
0x140091a0a  cmp     byte ptr [rcx+19h], 4
0x140091a0e  jb      short loc_140091A2D
0x140091a10  mov     rcx, [rcx+10h]
0x140091a14  lea     edx, [rbx+3Fh]
0x140091a17  mov     r9d, eax
0x140091a1a  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091a21  call    WPP_SF_d
0x140091a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140091a2d  cmp     rcx, rsi
0x140091a30  jz      short loc_140091A56
0x140091a32  test    byte ptr [rcx+1Ch], 1
0x140091a36  jz      short loc_140091A56
0x140091a38  cmp     byte ptr [rcx+19h], 5
0x140091a3c  jb      short loc_140091A56
0x140091a3e  mov     rcx, [rcx+10h]
0x140091a42  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091a49  mov     edx, 40h ; '@'
0x140091a4e  mov     r9d, ebx
0x140091a51  call    WPP_SF_d
0x140091a56  mov     rsi, [rsp+28h+arg_8]
0x140091a5b  mov     eax, ebx
0x140091a5d  mov     rbx, [rsp+28h+arg_0]
0x140091a62  add     rsp, 20h
0x140091a66  pop     rdi
0x140091a67  retn
```
