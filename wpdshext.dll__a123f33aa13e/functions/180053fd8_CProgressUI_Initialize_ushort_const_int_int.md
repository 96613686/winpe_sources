# CProgressUI::_Initialize(ushort const *,int,int)

- ea: `0x180053fd8`
- end: `0x180054223`
- name: `?_Initialize@CProgressUI@@QEAAJPEBGHH@Z`
- size: `587`
- prototype: `__int64 __fastcall(CProgressUI *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180016780`
- `0x1800311d8`
- `0x180049d20`
- `0x1800705f0`

## callees

- `0x180004110`
- `0x18002ff5c`
- `0x180053fd8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18005405d`
- `KERNEL32!CreateEventW` at `0x18005407a`
- `KERNEL32!CreateEventW` at `0x180054097`
- `KERNEL32!CreateEventW` at `0x1800540b4`
- `KERNEL32!CreateEventW` at `0x1800540d1`
- `KERNEL32!CreateEventW` at `0x1800540ee`
- `KERNEL32!CreateEventW` at `0x18005410b`
- `KERNEL32!CreateEventW` at `0x180054128`
- `KERNEL32!CreateEventW` at `0x180054145`
- `KERNEL32!CreateEventW` at `0x180054162`
- `KERNEL32!CreateEventW` at `0x18005417b`
- `KERNEL32!CreateEventW` at `0x18005405d`
- `KERNEL32!CreateEventW` at `0x18005407a`
- `KERNEL32!CreateEventW` at `0x180054097`
- `KERNEL32!CreateEventW` at `0x1800540b4`
- `KERNEL32!CreateEventW` at `0x1800540d1`
- `KERNEL32!CreateEventW` at `0x1800540ee`
- `KERNEL32!CreateEventW` at `0x18005410b`
- `KERNEL32!CreateEventW` at `0x180054128`
- `KERNEL32!CreateEventW` at `0x180054145`
- `KERNEL32!CreateEventW` at `0x180054162`
- `KERNEL32!CreateEventW` at `0x18005417b`
- `KERNEL32!CreateThread` at `0x1800541a9`
- `KERNEL32!CreateThread` at `0x1800541a9`
- `KERNEL32!WaitForMultipleObjects` at `0x1800541d6`
- `KERNEL32!WaitForMultipleObjects` at `0x1800541d6`

## pseudocode

```c
__int64 __fastcall CProgressUI::_Initialize(CProgressUI *this, const unsigned __int16 *a2)
{
  int v3; // eax
  int v4; // r10d
  int v5; // r11d
  unsigned int v6; // ebx
  HANDLE EventW; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE Thread; // rax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  v3 = StringCchCopyW((unsigned __int16 *)this + 866, 0x104u, a2);
  v6 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)v3);
    goto LABEL_20;
  }
  *((_DWORD *)this + 29) = v5;
  *((_DWORD *)this + 32) = v4;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
    goto LABEL_19;
  v8 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = v8;
  if ( !v8 )
    goto LABEL_19;
  v9 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
    goto LABEL_19;
  v10 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = v10;
  if ( !v10 )
    goto LABEL_19;
  v11 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 6) = v11;
  if ( !v11 )
    goto LABEL_19;
  v12 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 7) = v12;
  if ( !v12 )
    goto LABEL_19;
  v13 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 8) = v13;
  if ( !v13 )
    goto LABEL_19;
  v14 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 9) = v14;
  if ( !v14 )
    goto LABEL_19;
  v15 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = v15;
  if ( !v15 )
    goto LABEL_19;
  v16 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 11) = v16;
  if ( !v16 )
    goto LABEL_19;
  v17 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 12) = v17;
  if ( !v17 )
    goto LABEL_19;
  Thread = CreateThread(0, 0, ProgressUIThreadProc, this, 0, 0);
  *((_QWORD *)this + 1) = Thread;
  if ( Thread )
  {
    Handles[0] = *((HANDLE *)this + 2);
    Handles[1] = Thread;
    WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  }
  if ( !*((_DWORD *)this + 28) )
  {
LABEL_19:
    v6 = -2147467259;
LABEL_20:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180053fd8  mov     [rsp+arg_0], rbx
0x180053fdd  mov     [rsp+arg_8], rbp
0x180053fe2  push    rdi
0x180053fe3  sub     rsp, 40h
0x180053fe7  mov     r11d, r8d
0x180053fea  mov     rdi, rcx
0x180053fed  mov     r8, rdx; unsigned __int16 *
0x180053ff0  add     rcx, 6C4h; unsigned __int16 *
0x180053ff7  mov     edx, 104h; unsigned __int64
0x180053ffc  mov     r10d, r9d
0x180053fff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054004  lea     rbp, WPP_GLOBAL_Control
0x18005400b  mov     ebx, eax
0x18005400d  test    eax, eax
0x18005400f  jns     short loc_180054048
0x180054011  mov     rcx, cs:WPP_GLOBAL_Control
0x180054018  cmp     rcx, rbp
0x18005401b  jz      loc_1800541E7
0x180054021  test    byte ptr [rcx+1Ch], 2
0x180054025  jz      loc_1800541E7
0x18005402b  mov     rcx, [rcx+10h]
0x18005402f  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180054036  mov     edx, 73h ; 's'
0x18005403b  mov     r9d, eax
0x18005403e  call    WPP_SF_d
0x180054043  jmp     loc_1800541E7
0x180054048  xor     r9d, r9d; lpName
0x18005404b  mov     [rdi+74h], r11d
0x18005404f  xor     r8d, r8d; bInitialState
0x180054052  mov     [rdi+80h], r10d
0x180054059  xor     edx, edx; bManualReset
0x18005405b  xor     ecx, ecx; lpEventAttributes
0x18005405d  call    cs:__imp_CreateEventW
0x180054063  mov     [rdi+10h], rax
0x180054067  test    rax, rax
0x18005406a  jz      loc_1800541E2
0x180054070  xor     r9d, r9d; lpName
0x180054073  xor     r8d, r8d; bInitialState
0x180054076  xor     edx, edx; bManualReset
0x180054078  xor     ecx, ecx; lpEventAttributes
0x18005407a  call    cs:__imp_CreateEventW
0x180054080  mov     [rdi+18h], rax
0x180054084  test    rax, rax
0x180054087  jz      loc_1800541E2
0x18005408d  xor     r9d, r9d; lpName
0x180054090  xor     r8d, r8d; bInitialState
0x180054093  xor     edx, edx; bManualReset
0x180054095  xor     ecx, ecx; lpEventAttributes
0x180054097  call    cs:__imp_CreateEventW
0x18005409d  mov     [rdi+20h], rax
0x1800540a1  test    rax, rax
0x1800540a4  jz      loc_1800541E2
0x1800540aa  xor     r9d, r9d; lpName
0x1800540ad  xor     r8d, r8d; bInitialState
0x1800540b0  xor     edx, edx; bManualReset
0x1800540b2  xor     ecx, ecx; lpEventAttributes
0x1800540b4  call    cs:__imp_CreateEventW
0x1800540ba  mov     [rdi+28h], rax
0x1800540be  test    rax, rax
0x1800540c1  jz      loc_1800541E2
0x1800540c7  xor     r9d, r9d; lpName
0x1800540ca  xor     r8d, r8d; bInitialState
0x1800540cd  xor     edx, edx; bManualReset
0x1800540cf  xor     ecx, ecx; lpEventAttributes
0x1800540d1  call    cs:__imp_CreateEventW
0x1800540d7  mov     [rdi+30h], rax
0x1800540db  test    rax, rax
0x1800540de  jz      loc_1800541E2
0x1800540e4  xor     r9d, r9d; lpName
0x1800540e7  xor     r8d, r8d; bInitialState
0x1800540ea  xor     edx, edx; bManualReset
0x1800540ec  xor     ecx, ecx; lpEventAttributes
0x1800540ee  call    cs:__imp_CreateEventW
0x1800540f4  mov     [rdi+38h], rax
0x1800540f8  test    rax, rax
0x1800540fb  jz      loc_1800541E2
0x180054101  xor     r9d, r9d; lpName
0x180054104  xor     r8d, r8d; bInitialState
0x180054107  xor     edx, edx; bManualReset
0x180054109  xor     ecx, ecx; lpEventAttributes
0x18005410b  call    cs:__imp_CreateEventW
0x180054111  mov     [rdi+40h], rax
0x180054115  test    rax, rax
0x180054118  jz      loc_1800541E2
0x18005411e  xor     r9d, r9d; lpName
0x180054121  xor     r8d, r8d; bInitialState
0x180054124  xor     edx, edx; bManualReset
0x180054126  xor     ecx, ecx; lpEventAttributes
0x180054128  call    cs:__imp_CreateEventW
0x18005412e  mov     [rdi+48h], rax
0x180054132  test    rax, rax
0x180054135  jz      loc_1800541E2
0x18005413b  xor     r9d, r9d; lpName
0x18005413e  xor     r8d, r8d; bInitialState
0x180054141  xor     edx, edx; bManualReset
0x180054143  xor     ecx, ecx; lpEventAttributes
0x180054145  call    cs:__imp_CreateEventW
0x18005414b  mov     [rdi+50h], rax
0x18005414f  test    rax, rax
0x180054152  jz      loc_1800541E2
0x180054158  xor     r9d, r9d; lpName
0x18005415b  xor     r8d, r8d; bInitialState
0x18005415e  xor     edx, edx; bManualReset
0x180054160  xor     ecx, ecx; lpEventAttributes
0x180054162  call    cs:__imp_CreateEventW
0x180054168  mov     [rdi+58h], rax
0x18005416c  test    rax, rax
0x18005416f  jz      short loc_1800541E2
0x180054171  xor     r9d, r9d; lpName
0x180054174  xor     r8d, r8d; bInitialState
0x180054177  xor     edx, edx; bManualReset
0x180054179  xor     ecx, ecx; lpEventAttributes
0x18005417b  call    cs:__imp_CreateEventW
0x180054181  mov     [rdi+60h], rax
0x180054185  test    rax, rax
0x180054188  jz      short loc_1800541E2
0x18005418a  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180054193  lea     r8, ?ProgressUIThreadProc@@YAKPEAX@Z; lpStartAddress
0x18005419a  mov     r9, rdi; lpParameter
0x18005419d  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800541a5  xor     edx, edx; dwStackSize
0x1800541a7  xor     ecx, ecx; lpThreadAttributes
0x1800541a9  call    cs:__imp_CreateThread
0x1800541af  mov     [rdi+8], rax
0x1800541b3  test    rax, rax
0x1800541b6  jz      short loc_1800541DC
0x1800541b8  mov     rcx, [rdi+10h]
0x1800541bc  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800541c1  xor     r8d, r8d; bWaitAll
0x1800541c4  mov     [rsp+48h+Handles], rcx
0x1800541c9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800541cd  mov     [rsp+48h+var_10], rax
0x1800541d2  lea     ecx, [r8+2]; nCount
0x1800541d6  call    cs:__imp_WaitForMultipleObjects
0x1800541dc  cmp     dword ptr [rdi+70h], 0
0x1800541e0  jnz     short loc_180054211
0x1800541e2  mov     ebx, 80004005h
0x1800541e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541ee  cmp     rcx, rbp
0x1800541f1  jz      short loc_180054211
0x1800541f3  test    byte ptr [rcx+1Ch], 2
0x1800541f7  jz      short loc_180054211
0x1800541f9  mov     rcx, [rcx+10h]
0x1800541fd  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180054204  mov     edx, 74h ; 't'
0x180054209  mov     r9d, ebx
0x18005420c  call    WPP_SF_d
0x180054211  mov     rbp, [rsp+48h+arg_8]
0x180054216  mov     eax, ebx
0x180054218  mov     rbx, [rsp+48h+arg_0]
0x18005421d  add     rsp, 40h
0x180054221  pop     rdi
0x180054222  retn
```
