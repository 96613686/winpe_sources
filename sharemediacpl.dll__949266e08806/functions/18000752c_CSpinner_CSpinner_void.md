# CSpinner::~CSpinner(void)

- ea: `0x18000752c`
- end: `0x1800075ba`
- name: `??1CSpinner@@QEAA@XZ`
- size: `142`
- prototype: `void __fastcall(CSpinner *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000bd4c`
- `0x180011390`

## callees

- `0x18000752c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800075a4`
- `ole32!CoTaskMemFree` at `0x1800075a4`
- `USER32!KillTimer` at `0x180007554`
- `USER32!KillTimer` at `0x180007554`
- `USER32!DestroyWindow` at `0x180007563`
- `USER32!DestroyWindow` at `0x180007563`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180007587`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180007587`

## pseudocode

```c
void __fastcall CSpinner::~CSpinner(CSpinner *this)
{
  HWND v2; // rcx
  int i; // edi
  DirectUI::Value *v4; // rcx

  if ( *((_DWORD *)this + 1) )
  {
    *((_DWORD *)this + 1) = 0;
    KillTimer(*((HWND *)this + 4), 0x3E8u);
  }
  v2 = (HWND)*((_QWORD *)this + 4);
  if ( v2 )
    DestroyWindow(v2);
  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *((_DWORD *)this + 4); ++i )
    {
      v4 = *(DirectUI::Value **)(*((_QWORD *)this + 1) + 8LL * i);
      if ( v4 )
      {
        DirectUI::Value::Release(v4);
        *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 1));
  }
}

```

## disassembly

```asm
0x18000752c  mov     [rsp+arg_0], rbx
0x180007531  mov     [rsp+arg_8], rsi
0x180007536  push    rdi
0x180007537  sub     rsp, 20h
0x18000753b  cmp     dword ptr [rcx+4], 0
0x18000753f  mov     rbx, rcx
0x180007542  jz      short loc_18000755A
0x180007544  mov     dword ptr [rcx+4], 0
0x18000754b  mov     edx, 3E8h; uIDEvent
0x180007550  mov     rcx, [rcx+20h]; hWnd
0x180007554  call    cs:__imp_KillTimer
0x18000755a  mov     rcx, [rbx+20h]; hWnd
0x18000755e  test    rcx, rcx
0x180007561  jz      short loc_180007569
0x180007563  call    cs:__imp_DestroyWindow
0x180007569  cmp     qword ptr [rbx+8], 0
0x18000756e  jz      short loc_1800075AA
0x180007570  xor     edi, edi
0x180007572  cmp     [rbx+10h], edi
0x180007575  jle     short loc_1800075A0
0x180007577  mov     rax, [rbx+8]
0x18000757b  movsxd  rsi, edi
0x18000757e  mov     rcx, [rax+rsi*8]
0x180007582  test    rcx, rcx
0x180007585  jz      short loc_180007599
0x180007587  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000758d  mov     rax, [rbx+8]
0x180007591  mov     qword ptr [rax+rsi*8], 0
0x180007599  inc     edi
0x18000759b  cmp     edi, [rbx+10h]
0x18000759e  jl      short loc_180007577
0x1800075a0  mov     rcx, [rbx+8]; pv
0x1800075a4  call    cs:__imp_CoTaskMemFree
0x1800075aa  mov     rbx, [rsp+28h+arg_0]
0x1800075af  mov     rsi, [rsp+28h+arg_8]
0x1800075b4  add     rsp, 20h
0x1800075b8  pop     rdi
0x1800075b9  retn
```
