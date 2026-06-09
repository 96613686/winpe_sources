# NThreadingLibrary::TWorkCrew::InsertWorkItem(NThreadingLibrary::TWorkItem *)

- ea: `0x1400138cc`
- end: `0x1400139aa`
- name: `?InsertWorkItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z`
- size: `222`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400133fc`

## callees

- `0x1400138cc`
- `0x1400140b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400138e8`
- `KERNEL32!GetCurrentThreadId` at `0x1400138e8`
- `KERNEL32!EnterCriticalSection` at `0x1400138df`
- `KERNEL32!EnterCriticalSection` at `0x1400138df`
- `KERNEL32!LeaveCriticalSection` at `0x140013999`
- `KERNEL32!LeaveCriticalSection` at `0x140013999`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::InsertWorkItem(
        NThreadingLibrary::TWorkCrew *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // r10
  int v6; // edi
  struct NCoreLibrary::TLink *v7; // rdx
  signed __int32 v8; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  ++*((_DWORD *)this + 21);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(v5) = 0;
  *((_DWORD *)this + 20) = CurrentThreadId;
  if ( *((_DWORD *)this + 44) )
  {
    v6 = -2147467259;
  }
  else if ( *((_QWORD *)a2 + 10) )
  {
    v6 = 0;
    if ( *((_DWORD *)a2 + 18) )
      v6 = -2147024846;
  }
  else
  {
    v7 = (struct NCoreLibrary::TLink *)(((unsigned __int64)a2 + 32)
                                      & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64));
    if ( v7 )
    {
      if ( !*(_QWORD *)((((unsigned __int64)a2 + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64)) + 0x10)
        || (v6 = 0,
            !*(_QWORD *)((((unsigned __int64)a2 + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64))
                       + 0x18)) )
      {
        v6 = -2147467259;
      }
      if ( v6 >= 0 )
      {
        v6 = NCoreLibrary::TLink::Link(*((NCoreLibrary::TLink **)this + 16), v7);
        if ( v6 >= 0 )
        {
          *((_QWORD *)a2 + 10) = this;
          *(_QWORD *)((char *)a2 + 68) = v5;
          ++*((_DWORD *)this + 50);
          do
            v8 = *((_DWORD *)a2 + 2);
          while ( v8 != 0x7FFFFFFF && v8 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 2, v8 + 1, v8) );
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
  }
  if ( !--*((_DWORD *)this + 21) )
    *((_DWORD *)this + 20) = v5;
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400138cc  push    rbx
0x1400138ce  push    rbp
0x1400138cf  push    rsi
0x1400138d0  push    rdi
0x1400138d1  sub     rsp, 28h
0x1400138d5  mov     rbp, rcx
0x1400138d8  mov     rsi, rdx
0x1400138db  add     rcx, 28h ; '('; lpCriticalSection
0x1400138df  call    cs:__imp_EnterCriticalSection
0x1400138e5  inc     dword ptr [rbp+54h]
0x1400138e8  call    cs:__imp_GetCurrentThreadId
0x1400138ee  xor     r10d, r10d
0x1400138f1  mov     [rbp+50h], eax
0x1400138f4  cmp     [rbp+0B0h], r10d
0x1400138fb  jnz     loc_140013982
0x140013901  cmp     [rsi+50h], r10
0x140013905  jz      short loc_140013917
0x140013907  mov     edi, r10d
0x14001390a  cmp     [rsi+48h], r10d
0x14001390e  jz      short loc_140013987
0x140013910  mov     edi, 80070032h
0x140013915  jmp     short loc_140013987
0x140013917  mov     rax, rsi
0x14001391a  lea     rcx, [rsi+20h]
0x14001391e  neg     rax
0x140013921  sbb     rdx, rdx
0x140013924  and     rdx, rcx; struct NCoreLibrary::TLink *
0x140013927  jz      short loc_14001397B
0x140013929  cmp     [rdx+10h], r10
0x14001392d  jz      short loc_140013938
0x14001392f  mov     edi, r10d
0x140013932  cmp     [rdx+18h], r10
0x140013936  jnz     short loc_14001393D
0x140013938  mov     edi, 80004005h
0x14001393d  test    edi, edi
0x14001393f  js      short loc_140013987
0x140013941  mov     rcx, [rbp+80h]; this
0x140013948  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x14001394d  mov     edi, eax
0x14001394f  test    eax, eax
0x140013951  js      short loc_140013987
0x140013953  mov     [rsi+50h], rbp
0x140013957  mov     edx, 7FFFFFFFh
0x14001395c  mov     [rsi+44h], r10
0x140013960  inc     dword ptr [rbp+0C8h]
0x140013966  jmp     short loc_140013972
0x140013968  lea     ecx, [rax+1]
0x14001396b  lock cmpxchg [rsi+8], ecx
0x140013970  jz      short loc_140013987
0x140013972  mov     eax, [rsi+8]
0x140013975  cmp     eax, edx
0x140013977  jnz     short loc_140013968
0x140013979  jmp     short loc_140013987
0x14001397b  mov     edi, 80070057h
0x140013980  jmp     short loc_140013987
0x140013982  mov     edi, 80004005h
0x140013987  dec     dword ptr [rbp+54h]
0x14001398a  mov     ecx, [rbp+54h]
0x14001398d  test    ecx, ecx
0x14001398f  jnz     short loc_140013995
0x140013991  mov     [rbp+50h], r10d
0x140013995  lea     rcx, [rbp+28h]; lpCriticalSection
0x140013999  call    cs:__imp_LeaveCriticalSection
0x14001399f  mov     eax, edi
0x1400139a1  add     rsp, 28h
0x1400139a5  pop     rdi
0x1400139a6  pop     rsi
0x1400139a7  pop     rbp
0x1400139a8  pop     rbx
0x1400139a9  retn
```
