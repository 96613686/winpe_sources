# SNICreateWorkerThread

- ea: `0x383aafeb0`
- end: `0x383ab00b5`
- name: `SNICreateWorkerThread`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x383ab86f0`
- `0x383ab9940`

## callees

- `0x383846430`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383aafeb0`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383aaff4e`
- `KERNEL32!GetLastError` at `0x383ab003b`
- `KERNEL32!GetLastError` at `0x383aaff4e`
- `KERNEL32!GetLastError` at `0x383ab003b`
- `KERNEL32!CloseHandle` at `0x383ab0031`
- `KERNEL32!CloseHandle` at `0x383ab0031`
- `KERNEL32!CreateThread` at `0x383aaff3f`
- `KERNEL32!CreateThread` at `0x383aaff3f`

## pseudocode

```c
__int64 __fastcall SNICreateWorkerThread(__int64 a1)
{
  _QWORD *v2; // rax
  DWORD LastError; // ebx
  HANDLE Thread; // rax
  unsigned int v5; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48510[0] )
    bidScopeEnterA(&v8, off_383B48510[0], SNIProcessAddProviderOnWorker);
  v2 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 16);
  if ( !v2 )
  {
    LastError = 8;
    goto LABEL_8;
  }
  *v2 = SNIProcessAddProviderOnWorker;
  v2[1] = a1;
  Thread = CreateThread(0, 0x1000u, ThreadHandle<SNIThreadHandleAllocator>::ThreadProcAdapter, v2, 0, 0);
  if ( Thread )
  {
    if ( !CloseHandle(Thread) )
      GetLastError();
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
LABEL_8:
      if ( (bidGblFlags & 2) != 0 && off_383B45F08[0] )
      {
        v5 = SniErrorIdFromStringId(0xC3B4u);
        bidTraceA(off_383B43888[0], 4832256, off_383B45F08[0], 9, v5);
      }
      SNISetLastError(9, LastError, 50100);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B45F00[0] )
        bidTraceA(off_383B43880[0], 4834304, off_383B45F00[0], LastError, dwCreationFlags);
      if ( v8 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return LastError;
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B45EF8[0] )
    bidTraceA(off_383B43878[0], 4841472, off_383B45EF8[0], 0, dwCreationFlags);
  if ( v8 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 0;
}

```

## disassembly

```asm
0x383aafeb0  mov     [rsp+arg_0], rbx
0x383aafeb5  push    rdi
0x383aafeb6  sub     rsp, 30h
0x383aafeba  mov     eax, cs:_bidGblFlags
0x383aafec0  mov     rbx, rcx
0x383aafec3  mov     [rsp+38h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383aafecc  and     eax, 20004h
0x383aafed1  lea     rdi, ?SNIProcessAddProviderOnWorker@@YAPEAXPEAX@Z; SNIProcessAddProviderOnWorker(void *)
0x383aafed8  cmp     eax, 20004h
0x383aafedd  jnz     short loc_383AAFF02
0x383aafedf  mov     rax, cs:off_383B48510; "<SNICreateWorkerThread|API|SNI> pfnAsyn"...
0x383aafee6  test    rax, rax
0x383aafee9  jz      short loc_383AAFF02
0x383aafeeb  mov     rdx, cs:off_383B48510; "<SNICreateWorkerThread|API|SNI> pfnAsyn"...
0x383aafef2  mov     r9, rcx
0x383aafef5  lea     rcx, [rsp+38h+arg_8]
0x383aafefa  mov     r8, rdi
0x383aafefd  call    _bidScopeEnterA
0x383aaff02  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x383aaff09  mov     edx, 10h
0x383aaff0e  mov     rax, [rcx]
0x383aaff11  call    qword ptr [rax+58h]
0x383aaff14  test    rax, rax
0x383aaff17  jnz     short loc_383AAFF1E
0x383aaff19  lea     ebx, [rax+8]
0x383aaff1c  jmp     short loc_383AAFF5E
0x383aaff1e  xor     ecx, ecx; lpThreadAttributes
0x383aaff20  lea     r8, ?ThreadProcAdapter@?$ThreadHandle@USNIThreadHandleAllocator@@@@CAKPEAX@Z; lpStartAddress
0x383aaff27  mov     r9, rax; lpParameter
0x383aaff2a  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x383aaff2f  mov     edx, 1000h; dwStackSize
0x383aaff34  mov     [rax], rdi
0x383aaff37  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x383aaff3b  mov     [rax+8], rbx
0x383aaff3f  call    cs:__imp_CreateThread
0x383aaff45  test    rax, rax
0x383aaff48  jnz     loc_383AB002E
0x383aaff4e  call    cs:__imp_GetLastError
0x383aaff54  mov     ebx, eax
0x383aaff56  test    eax, eax
0x383aaff58  jz      loc_383AB0041
0x383aaff5e  test    byte ptr cs:_bidGblFlags, 2
0x383aaff65  jz      short loc_383AAFFA3
0x383aaff67  mov     rcx, cs:off_383B45F08; "<SNICreateWorkerThread|ERR|SNI> Provide"...
0x383aaff6e  test    rcx, rcx
0x383aaff71  jz      short loc_383AAFFA3
0x383aaff73  mov     ecx, 0C3B4h; unsigned int
0x383aaff78  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383aaff7d  mov     r8, cs:off_383B45F08; "<SNICreateWorkerThread|ERR|SNI> Provide"...
0x383aaff84  mov     rcx, cs:off_383B43888; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383aaff8b  mov     r9d, 9
0x383aaff91  mov     edx, 49BC00h
0x383aaff96  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x383aaff9a  mov     [rsp+38h+dwCreationFlags], eax
0x383aaff9e  call    _bidTraceA
0x383aaffa3  mov     r8d, 0C3B4h
0x383aaffa9  mov     edx, ebx
0x383aaffab  mov     ecx, 9
0x383aaffb0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383aaffb5  mov     r11d, cs:_bidGblFlags
0x383aaffbc  and     r11d, 20002h
0x383aaffc3  cmp     r11d, 20002h
0x383aaffca  jnz     short loc_383AAFFF3
0x383aaffcc  mov     rax, cs:off_383B45F00; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x383aaffd3  test    rax, rax
0x383aaffd6  jz      short loc_383AAFFF3
0x383aaffd8  mov     r8, cs:off_383B45F00; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x383aaffdf  mov     rcx, cs:off_383B43880; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383aaffe6  mov     r9d, ebx
0x383aaffe9  mov     edx, 49C400h
0x383aaffee  call    _bidTraceA
0x383aafff3  cmp     [rsp+38h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383aafff9  jz      short loc_383AB0021
0x383aafffb  test    byte ptr cs:_bidGblFlags, 4
0x383ab0002  jz      short loc_383AB0021
0x383ab0004  mov     rcx, cs:_bidID
0x383ab000b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab000f  jz      short loc_383AB0021
0x383ab0011  lea     r9, [rsp+38h+arg_8]
0x383ab0016  xor     r8d, r8d
0x383ab0019  xor     edx, edx
0x383ab001b  call    cs:off_383B15058
0x383ab0021  mov     eax, ebx
0x383ab0023  mov     rbx, [rsp+38h+arg_0]
0x383ab0028  add     rsp, 30h
0x383ab002c  pop     rdi
0x383ab002d  retn
0x383ab002e  mov     rcx, rax; hObject
0x383ab0031  call    cs:__imp_CloseHandle
0x383ab0037  test    eax, eax
0x383ab0039  jnz     short loc_383AB0041
0x383ab003b  call    cs:__imp_GetLastError
0x383ab0041  mov     eax, cs:_bidGblFlags
0x383ab0047  and     eax, 20002h
0x383ab004c  cmp     eax, 20002h
0x383ab0051  jnz     short loc_383AB007A
0x383ab0053  mov     rax, cs:off_383B45EF8; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x383ab005a  test    rax, rax
0x383ab005d  jz      short loc_383AB007A
0x383ab005f  mov     r8, cs:off_383B45EF8; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x383ab0066  mov     rcx, cs:off_383B43878; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab006d  xor     r9d, r9d
0x383ab0070  mov     edx, 49E000h
0x383ab0075  call    _bidTraceA
0x383ab007a  cmp     [rsp+38h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ab0080  jz      short loc_383AB00A8
0x383ab0082  test    byte ptr cs:_bidGblFlags, 4
0x383ab0089  jz      short loc_383AB00A8
0x383ab008b  mov     rcx, cs:_bidID
0x383ab0092  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab0096  jz      short loc_383AB00A8
0x383ab0098  lea     r9, [rsp+38h+arg_8]
0x383ab009d  xor     r8d, r8d
0x383ab00a0  xor     edx, edx
0x383ab00a2  call    cs:off_383B15058
0x383ab00a8  xor     eax, eax
0x383ab00aa  mov     rbx, [rsp+38h+arg_0]
0x383ab00af  add     rsp, 30h
0x383ab00b3  pop     rdi
0x383ab00b4  retn
```
