# CContentFolder::_DestroyElement(_ITEMIDLIST const *)

- ea: `0x1800474b8`
- end: `0x180047611`
- name: `?_DestroyElement@CContentFolder@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180043320`

## callees

- `0x18002ff5c`
- `0x180035590`
- `0x180041dcc`
- `0x180041f3c`
- `0x180041fa8`
- `0x1800474b8`
- `0x1800626b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004756d`
- `KERNEL32!GetLastError` at `0x18004756d`
- `KERNEL32!GlobalFree` at `0x1800474fc`
- `KERNEL32!GlobalFree` at `0x1800475e4`
- `KERNEL32!GlobalFree` at `0x1800474fc`
- `KERNEL32!GlobalFree` at `0x1800475e4`
- `KERNEL32!CreateThread` at `0x18004755d`
- `KERNEL32!CreateThread` at `0x18004755d`
- `KERNEL32!WaitForSingleObject` at `0x18004758a`
- `KERNEL32!WaitForSingleObject` at `0x18004758a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentFolder::_DestroyElement(void **this, const struct _ITEMIDLIST *a2)
{
  struct _IDA *v3; // rdi
  struct _IDA *v4; // rbx
  unsigned int v5; // edi
  struct _ITEMIDLIST *Thread; // rax
  signed int LastError; // eax
  const struct _ITEMIDLIST *v9; // [rsp+30h] [rbp-148h] BYREF
  _DWORD Parameter[72]; // [rsp+40h] [rbp-138h] BYREF

  v9 = a2;
  v3 = (struct _IDA *)HIDA_Create(this[8]);
  GlobalFree(0);
  v4 = v3;
  if ( !v3 )
  {
    v5 = -2147467259;
LABEL_10:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v5);
    goto LABEL_13;
  }
  if ( !v3->cidl )
  {
    v5 = -2147418113;
    goto LABEL_10;
  }
  v4 = 0;
  CDeleteThreadData::CDeleteThreadData((CDeleteThreadData *)Parameter, 0, 0x500u, (struct CContentFolder *)this, v3);
  Thread = (struct _ITEMIDLIST *)CreateThread(
                                   0,
                                   0,
                                   (LPTHREAD_START_ROUTINE)CContentContextMenuCB::s_DoDeleteThreadProc,
                                   Parameter,
                                   0,
                                   0);
  v9 = Thread;
  if ( Thread )
  {
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    v5 = Parameter[0];
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  ATL::CHandle::~CHandle((ATL::CHandle *)&v9);
  CDeleteThreadData::~CDeleteThreadData((CDeleteThreadData *)Parameter);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_10;
LABEL_13:
  GlobalFree(v4);
  return v5;
}

```

## disassembly

```asm
0x1800474b8  mov     [rsp+arg_10], rbx
0x1800474bd  mov     [rsp+arg_18], rsi
0x1800474c2  push    rdi
0x1800474c3  sub     rsp, 170h
0x1800474ca  mov     rax, cs:__security_cookie
0x1800474d1  xor     rax, rsp
0x1800474d4  mov     [rsp+178h+var_18], rax
0x1800474dc  mov     rsi, rcx
0x1800474df  mov     [rsp+178h+var_148], rdx
0x1800474e4  lea     r8, [rsp+178h+var_148]
0x1800474e9  mov     edx, 1
0x1800474ee  mov     rcx, [rcx+40h]; Src
0x1800474f2  call    HIDA_Create
0x1800474f7  mov     rdi, rax
0x1800474fa  xor     ecx, ecx; hMem
0x1800474fc  call    cs:__imp_GlobalFree
0x180047502  mov     rbx, rdi
0x180047505  test    rdi, rdi
0x180047508  jnz     short loc_180047514
0x18004750a  mov     edi, 80004005h
0x18004750f  jmp     loc_1800475AF
0x180047514  cmp     dword ptr [rdi], 0
0x180047517  jnz     short loc_180047523
0x180047519  mov     edi, 8000FFFFh
0x18004751e  jmp     loc_1800475AF
0x180047523  xor     ebx, ebx
0x180047525  mov     [rsp+178h+var_148], rbx
0x18004752a  mov     qword ptr [rsp+178h+dwCreationFlags], rdi; struct _IDA *
0x18004752f  mov     r9, rsi; struct CContentFolder *
0x180047532  xor     edx, edx; HWND
0x180047534  mov     r8d, 500h; unsigned int
0x18004753a  lea     rcx, [rsp+178h+Parameter]; this
0x18004753f  call    ??0CDeleteThreadData@@QEAA@PEAUHWND__@@IPEAVCContentFolder@@PEAU_IDA@@@Z; CDeleteThreadData::CDeleteThreadData(HWND__ *,uint,CContentFolder *,_IDA *)
0x180047544  mov     [rsp+178h+lpThreadId], rbx; lpThreadId
0x180047549  mov     [rsp+178h+dwCreationFlags], ebx; dwCreationFlags
0x18004754d  lea     r9, [rsp+178h+Parameter]; lpParameter
0x180047552  lea     r8, ?s_DoDeleteThreadProc@CContentContextMenuCB@@SAKPEAX@Z; lpStartAddress
0x180047559  xor     edx, edx; dwStackSize
0x18004755b  xor     ecx, ecx; lpThreadAttributes
0x18004755d  call    cs:__imp_CreateThread
0x180047563  mov     [rsp+178h+var_148], rax
0x180047568  test    rax, rax
0x18004756b  jnz     short loc_180047584
0x18004756d  call    cs:__imp_GetLastError
0x180047573  mov     edi, eax
0x180047575  test    eax, eax
0x180047577  jle     short loc_180047594
0x180047579  movzx   edi, ax
0x18004757c  or      edi, 80070000h
0x180047582  jmp     short loc_180047594
0x180047584  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180047587  mov     rcx, rax; hHandle
0x18004758a  call    cs:__imp_WaitForSingleObject
0x180047590  mov     edi, [rsp+178h+Parameter]
0x180047594  lea     rcx, [rsp+178h+var_148]; this
0x180047599  lea     rsi, [rsp+178h+Parameter]
0x18004759e  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x1800475a3  mov     rcx, rsi; this
0x1800475a6  call    ??1CDeleteThreadData@@QEAA@XZ; CDeleteThreadData::~CDeleteThreadData(void)
0x1800475ab  test    edi, edi
0x1800475ad  jns     short loc_1800475E1
0x1800475af  lea     rax, WPP_GLOBAL_Control
0x1800475b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475bd  cmp     rcx, rax
0x1800475c0  jz      short loc_1800475E1
0x1800475c2  test    byte ptr [rcx+1Ch], 2
0x1800475c6  jz      short loc_1800475E1
0x1800475c8  mov     edx, 0A2h
0x1800475cd  mov     r9d, edi
0x1800475d0  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800475d7  mov     rcx, [rcx+10h]
0x1800475db  call    WPP_SF_d
0x1800475e0  nop
0x1800475e1  mov     rcx, rbx; hMem
0x1800475e4  call    cs:__imp_GlobalFree
0x1800475ea  mov     eax, edi
0x1800475ec  mov     rcx, [rsp+178h+var_18]
0x1800475f4  xor     rcx, rsp; StackCookie
0x1800475f7  call    __security_check_cookie
0x1800475fc  lea     r11, [rsp+178h+var_8]
0x180047604  mov     rbx, [r11+20h]
0x180047608  mov     rsi, [r11+28h]
0x18004760c  mov     rsp, r11
0x18004760f  pop     rdi
0x180047610  retn
```
