# UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)

- ea: `0x18000e95c`
- end: `0x18000ea6e`
- name: `?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(UndockedComponentLoadEvent *this, const struct UndockedComponentInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180003760`
- `0x18000adb8`
- `0x18000b198`
- `0x18000e95c`

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
0x18000e95c  mov     [rsp+arg_0], rbx
0x18000e961  mov     [rsp+arg_8], rsi
0x18000e966  push    rdi; int
0x18000e967  sub     rsp, 20h
0x18000e96b  mov     eax, [rdx]
0x18000e96d  lea     rbx, [rcx+10h]
0x18000e971  mov     [rcx+8], eax
0x18000e974  mov     rsi, rcx
0x18000e977  mov     eax, [rdx+4]
0x18000e97a  mov     rdi, rdx
0x18000e97d  mov     [rcx+0Ch], eax
0x18000e980  mov     rcx, [rbx]; lpMem
0x18000e983  test    rcx, rcx
0x18000e986  jz      short loc_18000E994
0x18000e988  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e98d  mov     qword ptr [rbx], 0
0x18000e994  mov     rcx, [rdi+8]
0x18000e998  mov     rdx, rbx
0x18000e99b  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e9a0  mov     ebx, eax
0x18000e9a2  test    eax, eax
0x18000e9a4  jns     short loc_18000E9C4
0x18000e9a6  mov     edx, 38h ; '8'; void *
0x18000e9ab  mov     rcx, [rsp+28h]; this
0x18000e9b0  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e9b7  mov     r9d, eax; char *
0x18000e9ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9bf  jmp     loc_18000EA5C
0x18000e9c4  lea     rbx, [rsi+18h]
0x18000e9c8  mov     rcx, [rbx]; lpMem
0x18000e9cb  test    rcx, rcx
0x18000e9ce  jz      short loc_18000E9DC
0x18000e9d0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e9d5  mov     qword ptr [rbx], 0
0x18000e9dc  mov     rcx, [rdi+10h]
0x18000e9e0  mov     rdx, rbx
0x18000e9e3  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e9e8  mov     ebx, eax
0x18000e9ea  test    eax, eax
0x18000e9ec  jns     short loc_18000E9F5
0x18000e9ee  mov     edx, 39h ; '9'
0x18000e9f3  jmp     short loc_18000E9AB
0x18000e9f5  lea     rbx, [rsi+28h]
0x18000e9f9  mov     rcx, [rbx]; lpMem
0x18000e9fc  test    rcx, rcx
0x18000e9ff  jz      short loc_18000EA0D
0x18000ea01  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000ea06  mov     qword ptr [rbx], 0
0x18000ea0d  mov     rcx, [rdi+20h]
0x18000ea11  mov     rdx, rbx
0x18000ea14  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000ea19  mov     ebx, eax
0x18000ea1b  test    eax, eax
0x18000ea1d  jns     short loc_18000EA26
0x18000ea1f  mov     edx, 3Ah ; ':'
0x18000ea24  jmp     short loc_18000E9AB
0x18000ea26  lea     rbx, [rsi+20h]
0x18000ea2a  mov     rcx, [rbx]; lpMem
0x18000ea2d  test    rcx, rcx
0x18000ea30  jz      short loc_18000EA3E
0x18000ea32  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000ea37  mov     qword ptr [rbx], 0
0x18000ea3e  mov     rcx, [rdi+18h]
0x18000ea42  mov     rdx, rbx
0x18000ea45  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000ea4a  mov     ebx, eax
0x18000ea4c  test    eax, eax
0x18000ea4e  jns     short loc_18000EA5A
0x18000ea50  mov     edx, 3Bh ; ';'
0x18000ea55  jmp     loc_18000E9AB
0x18000ea5a  xor     ebx, ebx
0x18000ea5c  mov     rsi, [rsp+28h+arg_8]
0x18000ea61  mov     eax, ebx
0x18000ea63  mov     rbx, [rsp+28h+arg_0]
0x18000ea68  add     rsp, 20h
0x18000ea6c  pop     rdi
0x18000ea6d  retn
```
