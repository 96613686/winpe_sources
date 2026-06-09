# CTimer::Create(CHost *,CTimer * *)

- ea: `0x14000e384`
- end: `0x14000e4a5`
- name: `?Create@CTimer@@SAJPEAVCHost@@PEAPEAV1@@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct CHost *, struct CTimer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000757c`

## callees

- `0x140001008`
- `0x140001048`
- `0x14000e328`
- `0x14000e384`
- `0x14000e4ac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000e3dd`
- `KERNEL32!GetCurrentThreadId` at `0x14000e3dd`
- `KERNEL32!CreateThread` at `0x14000e449`
- `KERNEL32!CreateThread` at `0x14000e449`
- `KERNEL32!CreateEventA` at `0x14000e3f4`
- `KERNEL32!CreateEventA` at `0x14000e3f4`
- `KERNEL32!GetLastError` at `0x14000e403`
- `KERNEL32!GetLastError` at `0x14000e403`
- `KERNEL32!CloseHandle` at `0x14000e465`
- `KERNEL32!CloseHandle` at `0x14000e465`

## pseudocode

```c
__int64 __fastcall CTimer::Create(struct CHost *a1, struct CTimer **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  HANDLE EventA; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  HANDLE Thread; // rax
  int v10; // edx
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  bool v13; // sf

  v4 = operator new(0x38u);
  v5 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  v4[4] = 0;
  *v4 = 0;
  v4[6] = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_DWORD *)v4 + 6) = 0;
  *((_DWORD *)v4 + 11) = GetCurrentThreadId();
  v5[2] = a1;
  EventA = CreateEventA(0, 0, 0, 0);
  v5[6] = EventA;
  if ( EventA && (Thread = CreateThread(0, 0, CTimer::ThreadCallback, v5, 0, (LPDWORD)v5 + 10), (v5[4] = Thread) != 0) )
  {
    PumpWaitForSingleObject((void *)v5[6], v10, v11, v12);
    CloseHandle((HANDLE)v5[6]);
    v8 = *((_DWORD *)v5 + 6);
    v5[6] = 0;
    v13 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v13 = v8 < 0;
    }
    if ( !v13 )
    {
      *a2 = (struct CTimer *)v5;
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  CTimer::~CTimer((CTimer *)v5);
  operator delete(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e384  mov     [rsp+arg_0], rbx
0x14000e389  mov     [rsp+arg_8], rsi
0x14000e38e  push    rdi
0x14000e38f  sub     rsp, 30h
0x14000e393  mov     rbx, rcx
0x14000e396  mov     rsi, rdx
0x14000e399  mov     ecx, 38h ; '8'; Size
0x14000e39e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e3a3  mov     rdi, rax
0x14000e3a6  test    rax, rax
0x14000e3a9  jz      loc_14000E48E
0x14000e3af  mov     qword ptr [rax+20h], 0
0x14000e3b7  mov     qword ptr [rax], 0
0x14000e3be  mov     qword ptr [rax+30h], 0
0x14000e3c6  mov     qword ptr [rax+8], 0
0x14000e3ce  mov     qword ptr [rax+10h], 0
0x14000e3d6  mov     dword ptr [rax+18h], 0
0x14000e3dd  call    cs:__imp_GetCurrentThreadId
0x14000e3e3  mov     [rdi+2Ch], eax
0x14000e3e6  xor     r9d, r9d; lpName
0x14000e3e9  xor     r8d, r8d; bInitialState
0x14000e3ec  mov     [rdi+10h], rbx
0x14000e3f0  xor     edx, edx; bManualReset
0x14000e3f2  xor     ecx, ecx; lpEventAttributes
0x14000e3f4  call    cs:__imp_CreateEventA
0x14000e3fa  mov     [rdi+30h], rax
0x14000e3fe  test    rax, rax
0x14000e401  jnz     short loc_14000E42A
0x14000e403  call    cs:__imp_GetLastError
0x14000e409  mov     ebx, eax
0x14000e40b  test    eax, eax
0x14000e40d  jle     short loc_14000E418
0x14000e40f  movzx   ebx, ax
0x14000e412  or      ebx, 80070000h
0x14000e418  mov     rcx, rdi; this
0x14000e41b  call    ??1CTimer@@QEAA@XZ; CTimer::~CTimer(void)
0x14000e420  mov     rcx, rdi; Block
0x14000e423  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e428  jmp     short loc_14000E493
0x14000e42a  lea     rax, [rdi+28h]
0x14000e42e  mov     r9, rdi; lpParameter
0x14000e431  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14000e436  lea     r8, ?ThreadCallback@CTimer@@KAKPEAX@Z; lpStartAddress
0x14000e43d  xor     edx, edx; dwStackSize
0x14000e43f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000e447  xor     ecx, ecx; lpThreadAttributes
0x14000e449  call    cs:__imp_CreateThread
0x14000e44f  mov     [rdi+20h], rax
0x14000e453  test    rax, rax
0x14000e456  jz      short loc_14000E403
0x14000e458  mov     rcx, [rdi+30h]; void *
0x14000e45c  call    ?PumpWaitForSingleObject@@YAKPEAXHKK@Z; PumpWaitForSingleObject(void *,int,ulong,ulong)
0x14000e461  mov     rcx, [rdi+30h]; hObject
0x14000e465  call    cs:__imp_CloseHandle
0x14000e46b  mov     ebx, [rdi+18h]
0x14000e46e  mov     qword ptr [rdi+30h], 0
0x14000e476  test    ebx, ebx
0x14000e478  jle     short loc_14000E485
0x14000e47a  movzx   ebx, bx
0x14000e47d  or      ebx, 80070000h
0x14000e483  test    ebx, ebx
0x14000e485  js      short loc_14000E418
0x14000e487  mov     [rsi], rdi
0x14000e48a  xor     ebx, ebx
0x14000e48c  jmp     short loc_14000E493
0x14000e48e  mov     ebx, 8007000Eh
0x14000e493  mov     rsi, [rsp+38h+arg_8]
0x14000e498  mov     eax, ebx
0x14000e49a  mov     rbx, [rsp+38h+arg_0]
0x14000e49f  add     rsp, 30h
0x14000e4a3  pop     rdi
0x14000e4a4  retn
```
