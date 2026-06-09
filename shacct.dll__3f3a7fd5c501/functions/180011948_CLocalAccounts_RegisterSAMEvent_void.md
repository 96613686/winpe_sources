# CLocalAccounts::_RegisterSAMEvent(void)

- ea: `0x180011948`
- end: `0x1800119f4`
- name: `?_RegisterSAMEvent@CLocalAccounts@@IEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f410`

## callees

- `0x18000bcc0`
- `0x180011948`
- `0x180017010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x1800119b4`
- `SHCORE!SHCreateThread` at `0x1800119b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011971`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011971`
- `SAMLIB!SamRegisterObjectChangeNotification` at `0x180011988`
- `SAMLIB!SamRegisterObjectChangeNotification` at `0x180011988`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::_RegisterSAMEvent(CLocalAccounts *this)
{
  unsigned int Error; // ebx
  HANDLE EventW; // rax
  int v4; // ebx

  Error = -2147220991;
  if ( !*((_QWORD *)this + 13) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 13) = EventW;
    if ( EventW )
    {
      v4 = SamRegisterObjectChangeNotification(2, EventW);
      if ( v4 < 0 )
      {
        return v4 | 0x10000000u;
      }
      else
      {
        (*(void (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 8LL))(this);
        if ( SHCreateThread(CLocalAccounts::_NotifyThreadProc, this, 8u, 0) )
        {
          return 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          (*(void (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 16LL))(this);
        }
      }
    }
    else
    {
      return (unsigned int)ResultFromKnownLastError();
    }
  }
  return Error;
}

```

## disassembly

```asm
0x180011948  mov     [rsp+arg_0], rbx
0x18001194d  push    rdi
0x18001194e  sub     rsp, 20h
0x180011952  cmp     qword ptr [rcx+68h], 0
0x180011957  mov     rdi, rcx
0x18001195a  mov     ebx, 80040201h
0x18001195f  jnz     loc_1800119E7
0x180011965  xor     r9d, r9d; lpName
0x180011968  xor     r8d, r8d; bInitialState
0x18001196b  xor     ecx, ecx; lpEventAttributes
0x18001196d  lea     edx, [r9+1]; bManualReset
0x180011971  call    cs:__imp_CreateEventW
0x180011977  mov     [rdi+68h], rax
0x18001197b  test    rax, rax
0x18001197e  jz      short loc_1800119E0
0x180011980  mov     rdx, rax
0x180011983  mov     ecx, 2
0x180011988  call    cs:__imp_SamRegisterObjectChangeNotification
0x18001198e  mov     ebx, eax
0x180011990  test    eax, eax
0x180011992  js      short loc_1800119DA
0x180011994  mov     rax, [rdi]
0x180011997  mov     rcx, rdi
0x18001199a  mov     rax, [rax+8]
0x18001199e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a3  xor     r9d, r9d; pfnCallback
0x1800119a6  lea     rcx, ?_NotifyThreadProc@CLocalAccounts@@KAKPEAX@Z; pfnThreadProc
0x1800119ad  mov     rdx, rdi; pData
0x1800119b0  lea     r8d, [r9+8]; flags
0x1800119b4  call    cs:__imp_SHCreateThread
0x1800119ba  test    eax, eax
0x1800119bc  jz      short loc_1800119C2
0x1800119be  xor     ebx, ebx
0x1800119c0  jmp     short loc_1800119E7
0x1800119c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800119c7  mov     rcx, [rdi]
0x1800119ca  mov     ebx, eax
0x1800119cc  mov     rax, [rcx+10h]
0x1800119d0  mov     rcx, rdi
0x1800119d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119d8  jmp     short loc_1800119E7
0x1800119da  bts     ebx, 1Ch
0x1800119de  jmp     short loc_1800119E7
0x1800119e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800119e5  mov     ebx, eax
0x1800119e7  mov     eax, ebx
0x1800119e9  mov     rbx, [rsp+28h+arg_0]
0x1800119ee  add     rsp, 20h
0x1800119f2  pop     rdi
0x1800119f3  retn
```
