# UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)

- ea: `0x1400111a4`
- end: `0x1400112b6`
- name: `?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z`
- size: `274`
- prototype: `int(UndockedComponentLoadEvent *__hidden this, const struct UndockedComponentInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x140002ac0`
- `0x14000ce98`
- `0x14000d4cc`
- `0x1400111a4`

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
0x1400111a4  mov     [rsp+arg_0], rbx
0x1400111a9  mov     [rsp+arg_8], rsi
0x1400111ae  push    rdi; int
0x1400111af  sub     rsp, 20h
0x1400111b3  mov     eax, [rdx]
0x1400111b5  lea     rbx, [rcx+10h]
0x1400111b9  mov     [rcx+8], eax
0x1400111bc  mov     rsi, rcx
0x1400111bf  mov     eax, [rdx+4]
0x1400111c2  mov     rdi, rdx
0x1400111c5  mov     [rcx+0Ch], eax
0x1400111c8  mov     rcx, [rbx]; lpMem
0x1400111cb  test    rcx, rcx
0x1400111ce  jz      short loc_1400111DC
0x1400111d0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400111d5  mov     qword ptr [rbx], 0
0x1400111dc  mov     rcx, [rdi+8]
0x1400111e0  mov     rdx, rbx
0x1400111e3  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1400111e8  mov     ebx, eax
0x1400111ea  test    eax, eax
0x1400111ec  jns     short loc_14001120C
0x1400111ee  mov     edx, 38h ; '8'; void *
0x1400111f3  mov     rcx, [rsp+28h]; this
0x1400111f8  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x1400111ff  mov     r9d, eax; char *
0x140011202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011207  jmp     loc_1400112A4
0x14001120c  lea     rbx, [rsi+18h]
0x140011210  mov     rcx, [rbx]; lpMem
0x140011213  test    rcx, rcx
0x140011216  jz      short loc_140011224
0x140011218  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001121d  mov     qword ptr [rbx], 0
0x140011224  mov     rcx, [rdi+10h]
0x140011228  mov     rdx, rbx
0x14001122b  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140011230  mov     ebx, eax
0x140011232  test    eax, eax
0x140011234  jns     short loc_14001123D
0x140011236  mov     edx, 39h ; '9'
0x14001123b  jmp     short loc_1400111F3
0x14001123d  lea     rbx, [rsi+28h]
0x140011241  mov     rcx, [rbx]; lpMem
0x140011244  test    rcx, rcx
0x140011247  jz      short loc_140011255
0x140011249  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001124e  mov     qword ptr [rbx], 0
0x140011255  mov     rcx, [rdi+20h]
0x140011259  mov     rdx, rbx
0x14001125c  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140011261  mov     ebx, eax
0x140011263  test    eax, eax
0x140011265  jns     short loc_14001126E
0x140011267  mov     edx, 3Ah ; ':'
0x14001126c  jmp     short loc_1400111F3
0x14001126e  lea     rbx, [rsi+20h]
0x140011272  mov     rcx, [rbx]; lpMem
0x140011275  test    rcx, rcx
0x140011278  jz      short loc_140011286
0x14001127a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001127f  mov     qword ptr [rbx], 0
0x140011286  mov     rcx, [rdi+18h]
0x14001128a  mov     rdx, rbx
0x14001128d  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140011292  mov     ebx, eax
0x140011294  test    eax, eax
0x140011296  jns     short loc_1400112A2
0x140011298  mov     edx, 3Bh ; ';'
0x14001129d  jmp     loc_1400111F3
0x1400112a2  xor     ebx, ebx
0x1400112a4  mov     rsi, [rsp+28h+arg_8]
0x1400112a9  mov     eax, ebx
0x1400112ab  mov     rbx, [rsp+28h+arg_0]
0x1400112b0  add     rsp, 20h
0x1400112b4  pop     rdi
0x1400112b5  retn
```
