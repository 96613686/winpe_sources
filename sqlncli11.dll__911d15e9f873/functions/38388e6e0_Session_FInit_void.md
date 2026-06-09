# Session::FInit(void)

- ea: `0x38388e6e0`
- end: `0x38388e7c2`
- name: `?FInit@Session@@UEAAKXZ`
- size: `226`
- prototype: `unsigned int __fastcall(Session *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x383846430`
- `0x3838832d0`
- `0x38388e6e0`
- `0x38388e7d0`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x38388e75c`
- `KERNEL32!CreateEventA` at `0x38388e75c`
- `KERNEL32!GetLastError` at `0x383903e7f`
- `KERNEL32!GetLastError` at `0x383903f97`
- `KERNEL32!GetLastError` at `0x383903e7f`
- `KERNEL32!GetLastError` at `0x383903f97`
- `KERNEL32!CloseHandle` at `0x383903f7f`
- `KERNEL32!CloseHandle` at `0x383903f7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Session::FInit(struct CCriticalSectionNT_SNI **this)
{
  DWORD LastError; // edi
  __int64 v3; // rdi
  struct CCriticalSectionNT_SNI *v4; // rdi
  struct CCriticalSectionNT_SNI *EventA; // rax
  unsigned int v7; // eax
  struct CCriticalSectionNT_SNI *v8; // rcx
  struct CCriticalSectionNT_SNI *v9; // rcx
  BOOL v10; // eax
  int v11; // [rsp+20h] [rbp-28h]

  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48D68[0] && bidID != -1 )
  {
    v11 = (int)off_383B48D68[0];
    off_383B15048();
  }
  LastError = CCriticalSectionNT_SNI::Initialize(this + 7);
  if ( !LastError )
  {
    if ( !*((_BYTE *)this + 200) )
    {
LABEL_8:
      Smux::AddSessionRef(this[6]);
      if ( (bidGblFlags & 0x20002) == 0x20002 )
      {
        if ( off_383B47F90[0] )
          bidTraceA(off_383B45910[0], 535552, off_383B47F90[0], 0, v11);
      }
      return 0;
    }
    v3 = *((_QWORD *)this[7] + 2);
    if ( v3 )
      v4 = (struct CCriticalSectionNT_SNI *)(v3 + 32);
    else
      v4 = 0;
    EventA = (struct CCriticalSectionNT_SNI *)CreateEventA(0, 0, 0, 0);
    this[24] = EventA;
    if ( EventA )
    {
      this[23] = v4;
      goto LABEL_8;
    }
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_8;
    if ( (bidGblFlags & 2) != 0 && off_383B47F98[0] )
    {
      v7 = SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B45918[0], 527360, off_383B47F98[0], 2, v7);
    }
    SNISetLastError(2, LastError, 50100);
  }
  if ( this[7] )
  {
    v8 = this[7];
    if ( v8 )
      (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))v8)(v8, 1);
    this[7] = 0;
  }
  if ( *((_BYTE *)this + 200) )
  {
    v9 = this[24];
    if ( v9 )
    {
      v10 = CloseHandle(v9);
      this[24] = 0;
      this[23] = 0;
      if ( !v10 )
        GetLastError();
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B47F88[0] )
    bidTraceA(off_383B45908[0], 553984, off_383B47F88[0], LastError, v11);
  return LastError;
}

```

## disassembly

```asm
0x38388e6e0  mov     r11, rsp
0x38388e6e3  push    rdi
0x38388e6e4  sub     rsp, 40h
0x38388e6e8  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x38388e6f0  mov     [r11+10h], rbx
0x38388e6f4  mov     [r11+18h], rbp
0x38388e6f8  mov     [r11+20h], rsi
0x38388e6fc  mov     rbx, rcx
0x38388e6ff  mov     qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x38388e707  mov     eax, cs:_bidGblFlags
0x38388e70d  and     eax, 20004h
0x38388e712  xor     ebp, ebp
0x38388e714  cmp     eax, 20004h
0x38388e719  jz      loc_383903E2E
0x38388e71f  lea     rcx, [rbx+38h]; struct CCriticalSectionNT_SNI **
0x38388e723  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x38388e728  mov     edi, eax
0x38388e72a  test    eax, eax
0x38388e72c  jnz     loc_383903F4D
0x38388e732  cmp     [rbx+0C8h], bpl
0x38388e739  jz      short loc_38388E779
0x38388e73b  mov     rax, [rbx+38h]
0x38388e73f  mov     rdi, [rax+10h]
0x38388e743  test    rdi, rdi
0x38388e746  jz      loc_383903E77
0x38388e74c  add     rdi, 20h ; ' '
0x38388e750  jmp     short $+2
0x38388e752  xor     r9d, r9d; lpName
0x38388e755  xor     r8d, r8d; bInitialState
0x38388e758  xor     edx, edx; bManualReset
0x38388e75a  xor     ecx, ecx; lpEventAttributes
0x38388e75c  call    cs:__imp_CreateEventA
0x38388e762  mov     [rbx+0C0h], rax
0x38388e769  test    rax, rax
0x38388e76c  jz      loc_383903E7F
0x38388e772  mov     [rbx+0B8h], rdi
0x38388e779  mov     rcx, [rbx+30h]; this
0x38388e77d  call    ?AddSessionRef@Smux@@QEAAXXZ; Smux::AddSessionRef(void)
0x38388e782  mov     r11d, cs:_bidGblFlags
0x38388e789  and     r11d, 20002h
0x38388e790  cmp     r11d, 20002h
0x38388e797  jz      loc_383903EE8
0x38388e79d  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x38388e7a3  jnz     loc_383903F19
0x38388e7a9  xor     eax, eax
0x38388e7ab  jmp     short $+2
0x38388e7ad  mov     rbx, [rsp+48h+arg_8]
0x38388e7b2  mov     rbp, [rsp+48h+arg_10]
0x38388e7b7  mov     rsi, [rsp+48h+arg_18]
0x38388e7bc  add     rsp, 40h
0x38388e7c0  pop     rdi
0x38388e7c1  retn
0x383903e2e  mov     rax, cs:off_383B48D68; "<Session::FInit|API|SNI> \n"
0x383903e35  test    rax, rax
0x383903e38  jz      loc_38388E71F
0x383903e3e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383903e46  jz      loc_38388E71F
0x383903e4c  mov     [r11-20h], rbp
0x383903e50  mov     rax, cs:off_383B48D68; "<Session::FInit|API|SNI> \n"
0x383903e57  mov     [r11-28h], rax
0x383903e5b  lea     r9, [r11+8]
0x383903e5f  xor     r8d, r8d
0x383903e62  xor     edx, edx
0x383903e64  mov     rcx, cs:_bidID
0x383903e6b  call    cs:off_383B15048
0x383903e71  nop
0x383903e72  jmp     loc_38388E71F
0x383903e77  mov     rdi, rbp
0x383903e7a  jmp     loc_38388E752
0x383903e7f  call    cs:__imp_GetLastError
0x383903e85  mov     edi, eax
0x383903e87  test    eax, eax
0x383903e89  jz      loc_38388E779
0x383903e8f  test    byte ptr cs:_bidGblFlags, 2
0x383903e96  jz      short loc_383903ED4
0x383903e98  mov     rax, cs:off_383B47F98; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x383903e9f  test    rax, rax
0x383903ea2  jz      short loc_383903ED4
0x383903ea4  mov     ecx, 0C3B4h; unsigned int
0x383903ea9  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383903eae  mov     [rsp+48h+var_20], edi
0x383903eb2  mov     [rsp+48h+var_28], eax
0x383903eb6  mov     r9d, 2
0x383903ebc  mov     r8, cs:off_383B47F98; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x383903ec3  mov     edx, 80C00h
0x383903ec8  mov     rcx, cs:off_383B45918; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383903ecf  call    _bidTraceA
0x383903ed4  mov     r8d, 0C3B4h
0x383903eda  mov     edx, edi
0x383903edc  mov     ecx, 2
0x383903ee1  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383903ee6  jmp     short loc_383903F4D
0x383903ee8  mov     rax, cs:off_383B47F90; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x383903eef  test    rax, rax
0x383903ef2  jz      loc_38388E79D
0x383903ef8  xor     r9d, r9d
0x383903efb  mov     r8, cs:off_383B47F90; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x383903f02  mov     edx, 82C00h
0x383903f07  mov     rcx, cs:off_383B45910; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383903f0e  call    _bidTraceA
0x383903f13  nop
0x383903f14  jmp     loc_38388E79D
0x383903f19  test    byte ptr cs:_bidGblFlags, 4
0x383903f20  jz      loc_38388E7A9
0x383903f26  mov     rcx, cs:_bidID
0x383903f2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383903f31  jz      loc_38388E7A9
0x383903f37  lea     r9, [rsp+48h+arg_0]
0x383903f3c  xor     r8d, r8d
0x383903f3f  xor     edx, edx
0x383903f41  call    cs:off_383B15058
0x383903f47  nop
0x383903f48  jmp     loc_38388E7A9
0x383903f4d  cmp     [rbx+38h], rbp
0x383903f51  jz      short loc_383903F6A
0x383903f53  mov     rcx, [rbx+38h]
0x383903f57  test    rcx, rcx
0x383903f5a  jz      short loc_383903F66
0x383903f5c  mov     rax, [rcx]
0x383903f5f  mov     edx, 1
0x383903f64  call    qword ptr [rax]
0x383903f66  mov     [rbx+38h], rbp
0x383903f6a  cmp     [rbx+0C8h], bpl
0x383903f71  jz      short loc_383903F9D
0x383903f73  mov     rcx, [rbx+0C0h]; hObject
0x383903f7a  test    rcx, rcx
0x383903f7d  jz      short loc_383903F9D
0x383903f7f  call    cs:__imp_CloseHandle
0x383903f85  mov     [rbx+0C0h], rbp
0x383903f8c  mov     [rbx+0B8h], rbp
0x383903f93  test    eax, eax
0x383903f95  jnz     short loc_383903F9D
0x383903f97  call    cs:__imp_GetLastError
0x383903f9d  mov     eax, cs:_bidGblFlags
0x383903fa3  and     eax, 20002h
0x383903fa8  cmp     eax, 20002h
0x383903fad  jnz     short loc_383903FD7
0x383903faf  mov     rax, cs:off_383B47F88; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x383903fb6  test    rax, rax
0x383903fb9  jz      short loc_383903FD7
0x383903fbb  mov     r9d, edi
0x383903fbe  mov     r8, cs:off_383B47F88; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x383903fc5  mov     edx, 87400h
0x383903fca  mov     rcx, cs:off_383B45908; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383903fd1  call    _bidTraceA
0x383903fd6  nop
0x383903fd7  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383903fdd  jz      short loc_383904005
0x383903fdf  test    byte ptr cs:_bidGblFlags, 4
0x383903fe6  jz      short loc_383904005
0x383903fe8  mov     rcx, cs:_bidID
0x383903fef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383903ff3  jz      short loc_383904005
0x383903ff5  lea     r9, [rsp+48h+arg_0]
0x383903ffa  xor     r8d, r8d
0x383903ffd  xor     edx, edx
0x383903fff  call    cs:off_383B15058
0x383904005  mov     eax, edi
0x383904007  jmp     loc_38388E7AD
```
