# BlbReadFileFromTarget(ushort *,ushort * *,_LARGE_INTEGER *)

- ea: `0x14012458c`
- end: `0x140124821`
- name: `?BlbReadFileFromTarget@@YAJPEAGPEAPEAGPEAT_LARGE_INTEGER@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, union _LARGE_INTEGER *)`
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x14001f720`
- `0x140039170`
- `0x14005914c`
- `0x140071f1c`
- `0x1400f1a44`
- `0x1400f9e68`
- `0x140106f84`
- `0x1401070e0`
- `0x140107278`
- `0x140119a5c`
- `0x140120f88`

## callees

- `0x140006ca8`
- `0x140014260`
- `0x14003c434`
- `0x14012458c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x14012473a`
- `KERNEL32!ReadFile` at `0x14012473a`
- `KERNEL32!GetFileSizeEx` at `0x14012464a`
- `KERNEL32!GetFileSizeEx` at `0x14012464a`
- `KERNEL32!CreateFileW` at `0x1401245d5`
- `KERNEL32!CreateFileW` at `0x1401245d5`
- `KERNEL32!CloseHandle` at `0x1401247c8`
- `KERNEL32!CloseHandle` at `0x1401247c8`
- `KERNEL32!GetLastError` at `0x1401245e4`
- `KERNEL32!GetLastError` at `0x14012465b`
- `KERNEL32!GetLastError` at `0x140124744`
- `KERNEL32!GetLastError` at `0x1401245e4`
- `KERNEL32!GetLastError` at `0x14012465b`
- `KERNEL32!GetLastError` at `0x140124744`
- `ole32!CoTaskMemAlloc` at `0x14012470f`
- `ole32!CoTaskMemAlloc` at `0x14012470f`
- `ole32!CoTaskMemFree` at `0x140124790`
- `ole32!CoTaskMemFree` at `0x140124790`

## string_xrefs

- `0x14012479e`: `dwBytesRead == dwBytesToRead`

## pseudocode

```c
__int64 __fastcall BlbReadFileFromTarget(unsigned __int16 *a1, unsigned __int16 **a2, union _LARGE_INTEGER *a3)
{
  signed int v3; // ebx
  int v6; // r13d
  HANDLE FileW; // rax
  void *v8; // r12
  DWORD v9; // eax
  PVOID *v10; // rcx
  bool v11; // sf
  DWORD v12; // eax
  unsigned __int64 LowPart; // rdi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  DWORD LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  *a2 = 0;
  a3->QuadPart = 0;
  v6 = (int)a1;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileSizeEx(FileW, a3) )
    {
      if ( a3->HighPart || (LowPart = a3->LowPart, (LowPart & 1) != 0) )
      {
        v3 = -2139619288;
      }
      else if ( (int)LowPart + 2 >= (unsigned int)LowPart )
      {
        v14 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(LowPart + 2));
        v15 = v14;
        if ( v14 )
        {
          if ( ReadFile(v8, v14, LowPart, &NumberOfBytesRead, 0) )
          {
            if ( NumberOfBytesRead != (_DWORD)LowPart )
              BlbAssert("base\\stor\\blb\\wsbutil\\wsbfsutils.cpp", 0x8Du, "dwBytesRead == dwBytesToRead");
            *a2 = v15;
            v15[LowPart >> 1] = 0;
          }
          else
          {
            LastError = GetLastError();
            v3 = LastError;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                (unsigned int)WPP_78578e2f3df4302a56af778924a7199c_Traceguids,
                v6,
                LastError);
            }
            if ( v3 > 0 )
              v3 = (unsigned __int16)v3 | 0x80070000;
            CoTaskMemFree(v15);
          }
        }
        else
        {
          v3 = -2147024882;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_78578e2f3df4302a56af778924a7199c_Traceguids);
        }
        v3 = -2147024362;
      }
    }
    else
    {
      v12 = GetLastError();
      v3 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_78578e2f3df4302a56af778924a7199c_Traceguids,
          v6,
          v12);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    CloseHandle(v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  v9 = GetLastError();
  v3 = v9;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_78578e2f3df4302a56af778924a7199c_Traceguids,
      v6,
      v9);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_38:
    v11 = v3 < 0;
  }
  if ( v11 && v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    WPP_SF_Sd((unsigned int)v10[2], 14, (unsigned int)WPP_78578e2f3df4302a56af778924a7199c_Traceguids, v6, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14012458c  mov     rax, rsp
0x14012458f  mov     [rax+8], rbx
0x140124593  mov     [rax+18h], rbp
0x140124597  push    rsi
0x140124598  push    rdi
0x140124599  push    r12
0x14012459b  push    r13
0x14012459d  push    r14
0x14012459f  sub     rsp, 40h
0x1401245a3  xor     ebx, ebx
0x1401245a5  mov     rdi, r8
0x1401245a8  mov     [rdx], rbx
0x1401245ab  mov     r14, rdx
0x1401245ae  mov     [rax-38h], rbx
0x1401245b2  xor     r9d, r9d; lpSecurityAttributes
0x1401245b5  mov     [r8], rbx
0x1401245b8  mov     edx, 80000000h; dwDesiredAccess
0x1401245bd  mov     dword ptr [rax-40h], 80h
0x1401245c4  lea     r8d, [rbx+1]; dwShareMode
0x1401245c8  mov     r13, rcx
0x1401245cb  mov     [rax+10h], ebx
0x1401245ce  mov     dword ptr [rax-48h], 3
0x1401245d5  call    cs:__imp_CreateFileW
0x1401245db  mov     r12, rax
0x1401245de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401245e2  jnz     short loc_140124644
0x1401245e4  call    cs:__imp_GetLastError
0x1401245ea  mov     ebx, eax
0x1401245ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1401245f3  lea     rbp, WPP_GLOBAL_Control
0x1401245fa  cmp     rcx, rbp
0x1401245fd  jz      short loc_14012462E
0x1401245ff  test    byte ptr [rcx+1Ch], 1
0x140124603  jz      short loc_14012462E
0x140124605  cmp     byte ptr [rcx+19h], 2
0x140124609  jb      short loc_14012462E
0x14012460b  mov     rcx, [rcx+10h]
0x14012460f  lea     edx, [r12+0Bh]
0x140124614  mov     r9, r13
0x140124617  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x14012461b  lea     r8, WPP_78578e2f3df4302a56af778924a7199c_Traceguids
0x140124622  call    WPP_SF_Sd
0x140124627  mov     rcx, cs:WPP_GLOBAL_Control
0x14012462e  test    ebx, ebx
0x140124630  jle     loc_1401247D7
0x140124636  movzx   ebx, bx
0x140124639  or      ebx, 80070000h
0x14012463f  jmp     loc_1401247D5
0x140124644  mov     rdx, rdi; lpFileSize
0x140124647  mov     rcx, r12; hFile
0x14012464a  call    cs:__imp_GetFileSizeEx
0x140124650  lea     rbp, WPP_GLOBAL_Control
0x140124657  test    eax, eax
0x140124659  jnz     short loc_1401246AD
0x14012465b  call    cs:__imp_GetLastError
0x140124661  mov     ebx, eax
0x140124663  mov     rcx, cs:WPP_GLOBAL_Control
0x14012466a  cmp     rcx, rbp
0x14012466d  jz      short loc_140124697
0x14012466f  test    byte ptr [rcx+1Ch], 1
0x140124673  jz      short loc_140124697
0x140124675  cmp     byte ptr [rcx+19h], 2
0x140124679  jb      short loc_140124697
0x14012467b  mov     rcx, [rcx+10h]
0x14012467f  lea     r8, WPP_78578e2f3df4302a56af778924a7199c_Traceguids
0x140124686  mov     edx, 0Bh
0x14012468b  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x14012468f  mov     r9, r13
0x140124692  call    WPP_SF_Sd
0x140124697  test    ebx, ebx
0x140124699  jle     loc_1401247C5
0x14012469f  movzx   ebx, bx
0x1401246a2  or      ebx, 80070000h
0x1401246a8  jmp     loc_1401247C5
0x1401246ad  cmp     [rdi+4], ebx
0x1401246b0  jz      short loc_1401246BC
0x1401246b2  mov     ebx, 80780028h
0x1401246b7  jmp     loc_1401247C5
0x1401246bc  mov     edi, [rdi]
0x1401246be  test    dil, 1
0x1401246c2  jnz     short loc_1401246B2
0x1401246c4  lea     eax, [rdi+2]
0x1401246c7  cmp     eax, edi
0x1401246c9  jnb     short loc_14012470D
0x1401246cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401246d2  cmp     rcx, rbp
0x1401246d5  jz      short loc_140124703
0x1401246d7  test    byte ptr [rcx+1Ch], 1
0x1401246db  jz      short loc_140124703
0x1401246dd  cmp     byte ptr [rcx+19h], 2
0x1401246e1  jb      short loc_140124703
0x1401246e3  mov     rcx, [rcx+10h]
0x1401246e7  lea     r8, WPP_78578e2f3df4302a56af778924a7199c_Traceguids
0x1401246ee  mov     edx, 0Ch
0x1401246f3  mov     dword ptr [rsp+68h+lpOverlapped], 2
0x1401246fb  mov     r9d, edi
0x1401246fe  call    WPP_SF_dd
0x140124703  mov     ebx, 80070216h
0x140124708  jmp     loc_1401247C5
0x14012470d  mov     ecx, eax; cb
0x14012470f  call    cs:__imp_CoTaskMemAlloc
0x140124715  mov     rsi, rax
0x140124718  test    rax, rax
0x14012471b  jnz     short loc_140124727
0x14012471d  mov     ebx, 8007000Eh
0x140124722  jmp     loc_1401247C5
0x140124727  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14012472c  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x140124731  mov     r8d, edi; nNumberOfBytesToRead
0x140124734  mov     rdx, rsi; lpBuffer
0x140124737  mov     rcx, r12; hFile
0x14012473a  call    cs:__imp_ReadFile
0x140124740  test    eax, eax
0x140124742  jnz     short loc_140124798
0x140124744  call    cs:__imp_GetLastError
0x14012474a  mov     ebx, eax
0x14012474c  mov     rcx, cs:WPP_GLOBAL_Control
0x140124753  cmp     rcx, rbp
0x140124756  jz      short loc_140124780
0x140124758  test    byte ptr [rcx+1Ch], 1
0x14012475c  jz      short loc_140124780
0x14012475e  cmp     byte ptr [rcx+19h], 2
0x140124762  jb      short loc_140124780
0x140124764  mov     rcx, [rcx+10h]
0x140124768  lea     r8, WPP_78578e2f3df4302a56af778924a7199c_Traceguids
0x14012476f  mov     edx, 0Dh
0x140124774  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x140124778  mov     r9, r13
0x14012477b  call    WPP_SF_Sd
0x140124780  test    ebx, ebx
0x140124782  jle     short loc_14012478D
0x140124784  movzx   ebx, bx
0x140124787  or      ebx, 80070000h
0x14012478d  mov     rcx, rsi; pv
0x140124790  call    cs:__imp_CoTaskMemFree
0x140124796  jmp     short loc_1401247C5
0x140124798  cmp     [rsp+68h+NumberOfBytesRead], edi
0x14012479c  jz      short loc_1401247B6
0x14012479e  lea     r8, aDwbytesreadDwb; "dwBytesRead == dwBytesToRead"
0x1401247a5  mov     edx, 8Dh; unsigned int
0x1401247aa  lea     rcx, aBaseStorBlbWsb_2; "base\\stor\\blb\\wsbutil\\wsbfsutils.cp"...
0x1401247b1  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1401247b6  mov     rcx, rdi
0x1401247b9  mov     [r14], rsi
0x1401247bc  shr     rcx, 1
0x1401247bf  xor     eax, eax
0x1401247c1  mov     [rsi+rcx*2], ax
0x1401247c5  mov     rcx, r12; hObject
0x1401247c8  call    cs:__imp_CloseHandle
0x1401247ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1401247d5  test    ebx, ebx
0x1401247d7  jns     short loc_140124806
0x1401247d9  cmp     rcx, rbp
0x1401247dc  jz      short loc_140124806
0x1401247de  test    byte ptr [rcx+1Ch], 1
0x1401247e2  jz      short loc_140124806
0x1401247e4  cmp     byte ptr [rcx+19h], 2
0x1401247e8  jb      short loc_140124806
0x1401247ea  mov     rcx, [rcx+10h]
0x1401247ee  lea     r8, WPP_78578e2f3df4302a56af778924a7199c_Traceguids
0x1401247f5  mov     edx, 0Eh
0x1401247fa  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x1401247fe  mov     r9, r13
0x140124801  call    WPP_SF_Sd
0x140124806  lea     r11, [rsp+68h+var_28]
0x14012480b  mov     eax, ebx
0x14012480d  mov     rbx, [r11+30h]
0x140124811  mov     rbp, [r11+40h]
0x140124815  mov     rsp, r11
0x140124818  pop     r14
0x14012481a  pop     r13
0x14012481c  pop     r12
0x14012481e  pop     rdi
0x14012481f  pop     rsi
0x140124820  retn
```
