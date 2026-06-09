# DeviceObject::SetDevice(HSWDEVICE__ *,ushort const *)

- ea: `0x180015424`
- end: `0x1800154b3`
- name: `?SetDevice@DeviceObject@@AEAAJPEAUHSWDEVICE__@@PEBG@Z`
- size: `143`
- prototype: `int(DeviceObject *__hidden this, struct HSWDEVICE__ *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180014ed0`

## callees

- `0x180015424`
- `0x1800157d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001543d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001543d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001549b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001549b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001544c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001544c`

## pseudocode

```c
__int64 __fastcall DeviceObject::SetDevice(DeviceObject *this, struct HSWDEVICE__ *a2, const unsigned __int16 *a3)
{
  char *v3; // rbx
  unsigned int v8; // edi
  int v9; // eax

  v3 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)v3 + 11);
  *((_DWORD *)v3 + 10) = GetCurrentThreadId();
  if ( *((_QWORD *)this + 2) )
  {
    if ( (*((_DWORD *)v3 + 11))-- == 1 )
      *((_DWORD *)v3 + 10) = 0;
    v8 = -2147020579;
  }
  else
  {
    *((_QWORD *)this + 2) = a2;
    v9 = NCoreLibrary::TString::Update((DeviceObject *)((char *)this + 40), a3);
    --*((_DWORD *)v3 + 11);
    v8 = v9;
    if ( !*((_DWORD *)v3 + 11) )
      *((_DWORD *)v3 + 10) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  return v8;
}

```

## disassembly

```asm
0x180015424  push    rbx
0x180015426  push    rbp
0x180015427  push    rsi
0x180015428  push    rdi
0x180015429  sub     rsp, 28h
0x18001542d  lea     rbx, [rcx+30h]
0x180015431  mov     rdi, rcx
0x180015434  mov     rcx, rbx; lpCriticalSection
0x180015437  mov     rsi, r8
0x18001543a  mov     rbp, rdx
0x18001543d  call    cs:__imp_EnterCriticalSection
0x180015444  nop     dword ptr [rax+rax+00h]
0x180015449  inc     dword ptr [rbx+2Ch]
0x18001544c  call    cs:__imp_GetCurrentThreadId
0x180015453  nop     dword ptr [rax+rax+00h]
0x180015458  mov     [rbx+28h], eax
0x18001545b  cmp     qword ptr [rdi+10h], 0
0x180015460  jz      short loc_180015479
0x180015462  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180015466  mov     eax, [rbx+2Ch]
0x180015469  jnz     short loc_180015472
0x18001546b  mov     dword ptr [rbx+28h], 0
0x180015472  mov     edi, 800710DDh
0x180015477  jmp     short loc_180015498
0x180015479  lea     rcx, [rdi+28h]; this
0x18001547d  mov     [rdi+10h], rbp
0x180015481  mov     rdx, rsi; unsigned __int16 *
0x180015484  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180015489  dec     dword ptr [rbx+2Ch]
0x18001548c  mov     edi, eax
0x18001548e  mov     edx, [rbx+2Ch]
0x180015491  test    edx, edx
0x180015493  jnz     short loc_180015498
0x180015495  mov     [rbx+28h], edx
0x180015498  mov     rcx, rbx; lpCriticalSection
0x18001549b  call    cs:__imp_LeaveCriticalSection
0x1800154a2  nop     dword ptr [rax+rax+00h]
0x1800154a7  mov     eax, edi
0x1800154a9  add     rsp, 28h
0x1800154ad  pop     rdi
0x1800154ae  pop     rsi
0x1800154af  pop     rbp
0x1800154b0  pop     rbx
0x1800154b1  retn
```
