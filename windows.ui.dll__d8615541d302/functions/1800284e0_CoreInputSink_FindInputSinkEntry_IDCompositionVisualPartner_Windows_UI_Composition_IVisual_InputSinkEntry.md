# CoreInputSink::FindInputSinkEntry(IDCompositionVisualPartner *,Windows::UI::Composition::IVisual *,_InputSinkEntry * *)

- ea: `0x1800284e0`
- end: `0x18002860b`
- name: `?FindInputSinkEntry@CoreInputSink@@AEAA_NPEAUIDCompositionVisualPartner@@PEAUIVisual@Composition@UI@Windows@@PEAPEAU_InputSinkEntry@@@Z`
- size: `299`
- prototype: `bool __fastcall(CoreInputSink *__hidden this, struct IDCompositionVisualPartner *, struct Windows::UI::Composition::IVisual *, struct _InputSinkEntry **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002714c`

## callees

- `0x1800284e0`
- `0x18006c524`
- `0x180071d6c`
- `0x1800966cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002851a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002851a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285cd`

## string_xrefs

- `0x180028566`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\helper.cpp`

## pseudocode

```c
char __fastcall CoreInputSink::FindInputSinkEntry(
        CoreInputSink *this,
        struct IDCompositionVisualPartner *a2,
        struct Windows::UI::Composition::IVisual *a3,
        struct IDCompositionVisualPartner ***a4)
{
  DWORD CurrentThreadId; // eax
  struct IDCompositionVisualPartner **v9; // rbx
  char v10; // bp
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
      this,
      CurrentThreadId,
      a2,
      a3);
  }
  if ( (a3 == 0) == (a2 == 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\helper.cpp",
      (const char *)a4);
  v9 = (struct IDCompositionVisualPartner **)CoreInputSink::_pInputSinkList;
  v10 = 0;
  *a4 = 0;
  while ( v9 )
  {
    if ( v9[39] == a2 && a2 || v9[40] == a3 && a3 )
    {
      *a4 = v9;
      v10 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v11 = GetCurrentThreadId();
        WPP_SF_qDqqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, this, v11, v9, a2, a3);
      }
      return v10;
    }
    v9 = (struct IDCompositionVisualPartner **)*v9;
  }
  return v10;
}

```

## disassembly

```asm
0x1800284e0  push    rbx
0x1800284e2  push    rbp
0x1800284e3  push    rsi
0x1800284e4  push    rdi
0x1800284e5  push    r12
0x1800284e7  push    r14
0x1800284e9  push    r15
0x1800284eb  sub     rsp, 40h
0x1800284ef  mov     r14, r9
0x1800284f2  mov     rdi, r8
0x1800284f5  mov     rsi, rdx
0x1800284f8  mov     r15, rcx
0x1800284fb  mov     rax, cs:WPP_GLOBAL_Control
0x180028502  lea     r12, WPP_GLOBAL_Control
0x180028509  cmp     rax, r12
0x18002850c  jz      short loc_18002854D
0x18002850e  test    byte ptr [rax+1Ch], 40h
0x180028512  jz      short loc_18002854D
0x180028514  cmp     byte ptr [rax+19h], 4
0x180028518  jb      short loc_18002854D
0x18002851a  call    cs:__imp_GetCurrentThreadId
0x180028520  mov     rcx, cs:WPP_GLOBAL_Control
0x180028527  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x18002852e  mov     [rsp+78h+var_48], rdi
0x180028533  mov     edx, 13h
0x180028538  mov     [rsp+78h+var_50], rsi
0x18002853d  mov     r9, r15
0x180028540  mov     [rsp+78h+var_58], eax
0x180028544  mov     rcx, [rcx+10h]
0x180028548  call    WPP_SF_qDqq
0x18002854d  xor     ecx, ecx
0x18002854f  test    rsi, rsi
0x180028552  setz    cl
0x180028555  xor     eax, eax
0x180028557  test    rdi, rdi
0x18002855a  setz    al
0x18002855d  cmp     eax, ecx
0x18002855f  jnz     short loc_180028578
0x180028561  mov     rcx, [rsp+78h]; this
0x180028566  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002856d  mov     edx, 230h; void *
0x180028572  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180028578  mov     rbx, cs:?_pInputSinkList@CoreInputSink@@0PEAU_InputSinkEntry@@EA; _InputSinkEntry * CoreInputSink::_pInputSinkList
0x18002857f  xor     bpl, bpl
0x180028582  mov     qword ptr [r14], 0
0x180028589  test    rbx, rbx
0x18002858c  jz      short loc_1800285F9
0x18002858e  cmp     [rbx+138h], rsi
0x180028595  jnz     short loc_18002859C
0x180028597  test    rsi, rsi
0x18002859a  jnz     short loc_1800285AF
0x18002859c  cmp     [rbx+140h], rdi
0x1800285a3  jnz     short loc_1800285AA
0x1800285a5  test    rdi, rdi
0x1800285a8  jnz     short loc_1800285AF
0x1800285aa  mov     rbx, [rbx]
0x1800285ad  jmp     short loc_180028589
0x1800285af  mov     [r14], rbx
0x1800285b2  mov     bpl, 1
0x1800285b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800285bc  cmp     rax, r12
0x1800285bf  jz      short loc_1800285F9
0x1800285c1  test    byte ptr [rax+1Ch], 40h
0x1800285c5  jz      short loc_1800285F9
0x1800285c7  cmp     byte ptr [rax+19h], 4
0x1800285cb  jb      short loc_1800285F9
0x1800285cd  call    cs:__imp_GetCurrentThreadId
0x1800285d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285da  mov     r9, r15
0x1800285dd  mov     [rsp+78h+var_40], rdi
0x1800285e2  mov     [rsp+78h+var_48], rsi
0x1800285e7  mov     [rsp+78h+var_50], rbx
0x1800285ec  mov     rcx, [rcx+10h]
0x1800285f0  mov     [rsp+78h+var_58], eax
0x1800285f4  call    WPP_SF_qDqqq
0x1800285f9  mov     al, bpl
0x1800285fc  add     rsp, 40h
0x180028600  pop     r15
0x180028602  pop     r14
0x180028604  pop     r12
0x180028606  pop     rdi
0x180028607  pop     rsi
0x180028608  pop     rbp
0x180028609  pop     rbx
0x18002860a  retn
```
