# CObjIdIndexChangeNotifier::Initialize(ushort const *,CVolume *)

- ea: `0x180009698`
- end: `0x180009710`
- name: `?Initialize@CObjIdIndexChangeNotifier@@QEAAXPEBGPEAVCVolume@@@Z`
- size: `120`
- prototype: `void __fastcall(CObjIdIndexChangeNotifier *__hidden this, const unsigned __int16 *, struct CVolume *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009364`

## callees

- `0x180009698`
- `0x18000a038`
- `0x18000d038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800096c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800096c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096fc`

## pseudocode

```c
void __fastcall CObjIdIndexChangeNotifier::Initialize(
        CObjIdIndexChangeNotifier *this,
        const unsigned __int16 *a2,
        struct CVolume *a3)
{
  HANDLE EventW; // rax
  void (*v5)(void *, unsigned __int8); // rdx
  unsigned int v6; // r9d
  DWORD LastError; // eax
  void *v8; // rax
  DWORD v9; // eax

  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 1) = -1;
  *((_QWORD *)this + 284) = a3;
  _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  v8 = TrkRegisterWaitForSingleObjectEx(EventW, v5, this, v6, 4u);
  *((_QWORD *)this + 3) = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    TrkRaiseWin32Error(v9);
  }
}

```

## disassembly

```asm
0x180009698  push    rbx
0x18000969a  sub     rsp, 30h
0x18000969e  mov     rbx, rcx
0x1800096a1  mov     [rcx+20h], rdx
0x1800096a5  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x1800096ad  mov     [rcx+8E0h], r8
0x1800096b4  lock inc dword ptr [r8+8]
0x1800096b9  xor     r9d, r9d; lpName
0x1800096bc  xor     r8d, r8d; bInitialState
0x1800096bf  xor     edx, edx; bManualReset
0x1800096c1  xor     ecx, ecx; lpEventAttributes
0x1800096c3  call    cs:__imp_CreateEventW
0x1800096c9  mov     [rbx+10h], rax
0x1800096cd  test    rax, rax
0x1800096d0  jnz     short loc_1800096E0
0x1800096d2  call    cs:__imp_GetLastError
0x1800096d8  mov     ecx, eax; int
0x1800096da  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x1800096e0  mov     r8, rbx; void *
0x1800096e3  mov     [rsp+38h+var_18], 4; unsigned int
0x1800096eb  mov     rcx, rax; hObject
0x1800096ee  call    ?TrkRegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z; TrkRegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)
0x1800096f3  mov     [rbx+18h], rax
0x1800096f7  test    rax, rax
0x1800096fa  jnz     short loc_18000970A
0x1800096fc  call    cs:__imp_GetLastError
0x180009702  mov     ecx, eax; int
0x180009704  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000970a  add     rsp, 30h
0x18000970e  pop     rbx
0x18000970f  retn
```
