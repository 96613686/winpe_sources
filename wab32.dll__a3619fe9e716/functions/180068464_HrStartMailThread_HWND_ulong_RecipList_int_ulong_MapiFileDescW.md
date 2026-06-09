# HrStartMailThread(HWND__ *,ulong,_RecipList *,int,ulong,MapiFileDescW *)

- ea: `0x180068464`
- end: `0x180068530`
- name: `?HrStartMailThread@@YAJPEAUHWND__@@KPEAU_RecipList@@HKPEAUMapiFileDescW@@@Z`
- size: `204`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, struct _RecipList *@<r8>, int@<r9d>, unsigned int, struct MapiFileDescW *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18003d660`
- `0x18003d740`
- `0x18003d7e0`
- `0x18003d850`
- `0x180067c08`

## callees

- `0x180068464`
- `0x180069e24`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800684e5`
- `KERNEL32!CreateThread` at `0x1800684e5`
- `KERNEL32!LocalAlloc` at `0x180068483`
- `KERNEL32!LocalAlloc` at `0x180068483`
- `KERNEL32!LocalFree` at `0x18006851d`
- `KERNEL32!LocalFree` at `0x18006851d`
- `KERNEL32!CloseHandle` at `0x1800684f5`
- `KERNEL32!CloseHandle` at `0x1800684f5`

## pseudocode

```c
__int64 __fastcall HrStartMailThread(
        HWND hWnd,
        int a2,
        struct _RecipList *a3,
        int a4,
        unsigned int a5,
        struct MapiFileDescW *a6)
{
  _QWORD *v10; // rax
  void *v11; // rbx
  HANDLE Thread; // rax
  unsigned int v13; // edi
  DWORD ThreadId[14]; // [rsp+30h] [rbp-38h] BYREF

  v10 = LocalAlloc(0x40u, 0x30u);
  v11 = v10;
  if ( !v10 )
    goto LABEL_4;
  *((_DWORD *)v10 + 9) = a5;
  v10[5] = a6;
  *v10 = hWnd;
  *((_DWORD *)v10 + 2) = a2;
  v10[2] = a3;
  *((_DWORD *)v10 + 8) = a4;
  v10[3] = 0;
  ThreadId[0] = 0;
  Thread = CreateThread(0, 0, MailThreadProc, v10, 0, ThreadId);
  if ( Thread )
  {
    v13 = 0;
    CloseHandle(Thread);
  }
  else
  {
LABEL_4:
    v13 = -2147467259;
    ShowMessageBox(hWnd, 4291, 48);
    if ( v11 )
      LocalFree(v11);
  }
  return v13;
}

```

## disassembly

```asm
0x180068464  push    rbx
0x180068466  push    rbp
0x180068467  push    rsi
0x180068468  push    rdi
0x180068469  push    r14
0x18006846b  sub     rsp, 40h
0x18006846f  mov     r14d, edx
0x180068472  mov     rsi, rcx
0x180068475  mov     edx, 30h ; '0'; uBytes
0x18006847a  mov     edi, r9d
0x18006847d  mov     rbp, r8
0x180068480  lea     ecx, [rdx+10h]; uFlags
0x180068483  call    cs:__imp_LocalAlloc
0x180068489  mov     rbx, rax
0x18006848c  test    rax, rax
0x18006848f  jz      short loc_1800684FD
0x180068491  mov     ecx, [rsp+68h+arg_20]
0x180068498  lea     r8, ?MailThreadProc@@YAKPEAX@Z; lpStartAddress
0x18006849f  mov     [rax+24h], ecx
0x1800684a2  mov     r9, rbx; lpParameter
0x1800684a5  mov     rcx, [rsp+68h+arg_28]
0x1800684ad  xor     edx, edx; dwStackSize
0x1800684af  mov     [rax+28h], rcx
0x1800684b3  xor     ecx, ecx; lpThreadAttributes
0x1800684b5  mov     [rax], rsi
0x1800684b8  mov     [rax+8], r14d
0x1800684bc  mov     [rax+10h], rbp
0x1800684c0  mov     [rax+20h], edi
0x1800684c3  mov     qword ptr [rax+18h], 0
0x1800684cb  lea     rax, [rsp+68h+ThreadId]
0x1800684d0  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800684d5  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800684dd  mov     [rsp+68h+ThreadId], 0
0x1800684e5  call    cs:__imp_CreateThread
0x1800684eb  test    rax, rax
0x1800684ee  jz      short loc_1800684FD
0x1800684f0  xor     edi, edi
0x1800684f2  mov     rcx, rax; hObject
0x1800684f5  call    cs:__imp_CloseHandle
0x1800684fb  jmp     short loc_180068523
0x1800684fd  mov     edx, 10C3h; int
0x180068502  mov     r8d, 30h ; '0'; int
0x180068508  mov     rcx, rsi; hWnd
0x18006850b  mov     edi, 80004005h
0x180068510  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x180068515  test    rbx, rbx
0x180068518  jz      short loc_180068523
0x18006851a  mov     rcx, rbx; hMem
0x18006851d  call    cs:__imp_LocalFree
0x180068523  mov     eax, edi
0x180068525  add     rsp, 40h
0x180068529  pop     r14
0x18006852b  pop     rdi
0x18006852c  pop     rsi
0x18006852d  pop     rbp
0x18006852e  pop     rbx
0x18006852f  retn
```
