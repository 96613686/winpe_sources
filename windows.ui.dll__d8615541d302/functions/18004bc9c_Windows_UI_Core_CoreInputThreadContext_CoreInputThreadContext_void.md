# Windows::UI::Core::CoreInputThreadContext::~CoreInputThreadContext(void)

- ea: `0x18004bc9c`
- end: `0x18004bd19`
- name: `??1CoreInputThreadContext@Core@UI@Windows@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(Windows::UI::Core::CoreInputThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180096a90`

## callees

- `0x18004bc9c`
- `0x180050360`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004bce0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004bce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bcaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bcaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcf7`

## string_xrefs

- `0x18004bcbf`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\inputthreadcontext.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Core::CoreInputThreadContext::~CoreInputThreadContext(
        Windows::UI::Core::CoreInputThreadContext *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::UI::Core::CoreInputThreadContext::`vftable';
  if ( GetCurrentThreadId() == *((_DWORD *)this + 4) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\inputthreadcontext.cpp",
      (const char *)0x8000FFFFLL,
      v4);
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    CloseThreadpoolWait(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18004bc9c  push    rbx; int
0x18004bc9e  sub     rsp, 20h
0x18004bca2  lea     rax, ??_7CoreInputThreadContext@Core@UI@Windows@@6B@; const Windows::UI::Core::CoreInputThreadContext::`vftable'
0x18004bca9  mov     rbx, rcx
0x18004bcac  mov     [rcx], rax
0x18004bcaf  call    cs:__imp_GetCurrentThreadId
0x18004bcb5  cmp     eax, [rbx+10h]
0x18004bcb8  jnz     short loc_18004BCD7
0x18004bcba  mov     rcx, [rsp+28h]; this
0x18004bcbf  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004bcc6  mov     r9d, 8000FFFFh; char *
0x18004bccc  mov     edx, 14Ah; void *
0x18004bcd1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004bcd7  mov     rcx, [rbx+30h]; pwa
0x18004bcdb  test    rcx, rcx
0x18004bcde  jz      short loc_18004BCEE
0x18004bce0  call    cs:__imp_CloseThreadpoolWait
0x18004bce6  mov     qword ptr [rbx+30h], 0
0x18004bcee  mov     rcx, [rbx+28h]; hObject
0x18004bcf2  test    rcx, rcx
0x18004bcf5  jz      short loc_18004BD05
0x18004bcf7  call    cs:__imp_CloseHandle
0x18004bcfd  mov     qword ptr [rbx+28h], 0
0x18004bd05  mov     dword ptr [rbx+10h], 0
0x18004bd0c  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18004bd13  add     rsp, 20h
0x18004bd17  pop     rbx
0x18004bd18  retn
```
