# UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)

- ea: `0x18000e9b0`
- end: `0x18000eac2`
- name: `?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z`
- size: `274`
- prototype: `int(UndockedComponentLoadEvent *__hidden this, const struct UndockedComponentInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x180003760`
- `0x18000ae0c`
- `0x18000b1ec`
- `0x18000e9b0`

## pseudocode

```c
__int64 __fastcall UndockedComponentLoadEvent::Init(
        UndockedComponentLoadEvent *this,
        const struct UndockedComponentInfo *a2)
{
  _QWORD *v2; // rbx
  void *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (_QWORD *)((char *)this + 16);
  *((_DWORD *)this + 2) = *(_DWORD *)a2;
  *((_DWORD *)this + 3) = *((_DWORD *)a2 + 1);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    SusFree(v5);
    *v2 = 0;
  }
  v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 1), v2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (void *)*((_QWORD *)this + 3);
    if ( v9 )
    {
      SusFree(v9);
      *((_QWORD *)this + 3) = 0;
    }
    v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 2), (char *)this + 24);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v10 = (void *)*((_QWORD *)this + 5);
      if ( v10 )
      {
        SusFree(v10);
        *((_QWORD *)this + 5) = 0;
      }
      v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 4), (char *)this + 40);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v11 = (void *)*((_QWORD *)this + 4);
        if ( v11 )
        {
          SusFree(v11);
          *((_QWORD *)this + 4) = 0;
        }
        v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 3), (char *)this + 32);
        v7 = v6;
        if ( v6 >= 0 )
          return 0;
        v8 = 59;
      }
      else
      {
        v8 = 58;
      }
    }
    else
    {
      v8 = 57;
    }
  }
  else
  {
    v8 = 56;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
    (const char *)(unsigned int)v6,
    v13);
  return v7;
}

```

## disassembly

```asm
0x18000e9b0  mov     [rsp+arg_0], rbx
0x18000e9b5  mov     [rsp+arg_8], rsi
0x18000e9ba  push    rdi; int
0x18000e9bb  sub     rsp, 20h
0x18000e9bf  mov     eax, [rdx]
0x18000e9c1  lea     rbx, [rcx+10h]
0x18000e9c5  mov     [rcx+8], eax
0x18000e9c8  mov     rsi, rcx
0x18000e9cb  mov     eax, [rdx+4]
0x18000e9ce  mov     rdi, rdx
0x18000e9d1  mov     [rcx+0Ch], eax
0x18000e9d4  mov     rcx, [rbx]; lpMem
0x18000e9d7  test    rcx, rcx
0x18000e9da  jz      short loc_18000E9E8
0x18000e9dc  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e9e1  mov     qword ptr [rbx], 0
0x18000e9e8  mov     rcx, [rdi+8]
0x18000e9ec  mov     rdx, rbx
0x18000e9ef  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e9f4  mov     ebx, eax
0x18000e9f6  test    eax, eax
0x18000e9f8  jns     short loc_18000EA18
0x18000e9fa  mov     edx, 38h ; '8'; void *
0x18000e9ff  mov     rcx, [rsp+28h]; this
0x18000ea04  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000ea0b  mov     r9d, eax; char *
0x18000ea0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea13  jmp     loc_18000EAB0
0x18000ea18  lea     rbx, [rsi+18h]
0x18000ea1c  mov     rcx, [rbx]; lpMem
0x18000ea1f  test    rcx, rcx
0x18000ea22  jz      short loc_18000EA30
0x18000ea24  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000ea29  mov     qword ptr [rbx], 0
0x18000ea30  mov     rcx, [rdi+10h]
0x18000ea34  mov     rdx, rbx
0x18000ea37  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000ea3c  mov     ebx, eax
0x18000ea3e  test    eax, eax
0x18000ea40  jns     short loc_18000EA49
0x18000ea42  mov     edx, 39h ; '9'
0x18000ea47  jmp     short loc_18000E9FF
0x18000ea49  lea     rbx, [rsi+28h]
0x18000ea4d  mov     rcx, [rbx]; lpMem
0x18000ea50  test    rcx, rcx
0x18000ea53  jz      short loc_18000EA61
0x18000ea55  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000ea5a  mov     qword ptr [rbx], 0
0x18000ea61  mov     rcx, [rdi+20h]
0x18000ea65  mov     rdx, rbx
0x18000ea68  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000ea6d  mov     ebx, eax
0x18000ea6f  test    eax, eax
0x18000ea71  jns     short loc_18000EA7A
0x18000ea73  mov     edx, 3Ah ; ':'
0x18000ea78  jmp     short loc_18000E9FF
0x18000ea7a  lea     rbx, [rsi+20h]
0x18000ea7e  mov     rcx, [rbx]; lpMem
0x18000ea81  test    rcx, rcx
0x18000ea84  jz      short loc_18000EA92
0x18000ea86  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000ea8b  mov     qword ptr [rbx], 0
0x18000ea92  mov     rcx, [rdi+18h]
0x18000ea96  mov     rdx, rbx
0x18000ea99  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000ea9e  mov     ebx, eax
0x18000eaa0  test    eax, eax
0x18000eaa2  jns     short loc_18000EAAE
0x18000eaa4  mov     edx, 3Bh ; ';'
0x18000eaa9  jmp     loc_18000E9FF
0x18000eaae  xor     ebx, ebx
0x18000eab0  mov     rsi, [rsp+28h+arg_8]
0x18000eab5  mov     eax, ebx
0x18000eab7  mov     rbx, [rsp+28h+arg_0]
0x18000eabc  add     rsp, 20h
0x18000eac0  pop     rdi
0x18000eac1  retn
```
