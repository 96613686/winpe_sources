# CSilentProcessExitReport::SetProcessInformation(ulong,ulong,ulong)

- ea: `0x1800111c0`
- end: `0x1800113f4`
- name: `?SetProcessInformation@CSilentProcessExitReport@@AEAAJKKK@Z`
- size: `564`
- prototype: `__int64 __fastcall(CSilentProcessExitReport *this, int, int, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180010234`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x18000983c`
- `0x1800111c0`
- `0x180011fa8`
- `0x180012718`
- `0x180013b38`
- `0x180013c94`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x1800111e5`
- `KERNEL32!OpenProcess` at `0x180011250`
- `KERNEL32!OpenProcess` at `0x180011335`
- `KERNEL32!OpenProcess` at `0x1800111e5`
- `KERNEL32!OpenProcess` at `0x180011250`
- `KERNEL32!OpenProcess` at `0x180011335`
- `KERNEL32!GetLastError` at `0x18001120e`
- `KERNEL32!GetLastError` at `0x18001126e`
- `KERNEL32!GetLastError` at `0x180011355`
- `KERNEL32!GetLastError` at `0x18001120e`
- `KERNEL32!GetLastError` at `0x18001126e`
- `KERNEL32!GetLastError` at `0x180011355`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSilentProcessExitReport::SetProcessInformation(
        CSilentProcessExitReport *this,
        int a2,
        int a3,
        DWORD a4)
{
  void **v4; // rbx
  HANDLE v6; // rax
  void *v7; // rcx
  DWORD LastError; // eax
  unsigned int v9; // eax
  HANDLE v10; // rax
  DWORD v11; // eax
  int ProcessPathFromHandle; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  const unsigned __int16 **v16; // rsi
  const unsigned __int16 *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  HANDLE v21; // rax
  void *v22; // rcx
  DWORD v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  const unsigned __int16 *v27; // rax

  *(_DWORD *)this = a2;
  v4 = (void **)((char *)this + 24);
  *((_DWORD *)this + 2) = a3;
  *((_DWORD *)this + 1) = a4;
  v6 = OpenProcess(0x410u, 0, a4);
  tlx::unique_any<tlx::file_handle_traits>::reset(v4, v6);
  v7 = *v4;
  if ( (unsigned __int64)*v4 + 1 > 1 )
    goto LABEL_10;
  LastError = GetLastError();
  v9 = ERROR_HR_FROM_WIN32(LastError);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, v9);
  v10 = OpenProcess(0x1000u, 0, *((_DWORD *)this + 1));
  tlx::unique_any<tlx::file_handle_traits>::reset(v4, v10);
  v7 = *v4;
  if ( (unsigned __int64)*v4 + 1 > 1 )
  {
LABEL_10:
    v16 = (const unsigned __int16 **)((char *)this + 32);
    ProcessPathFromHandle = UtilGetProcessPathFromHandle(v7);
    v13 = ProcessPathFromHandle;
    if ( ProcessPathFromHandle >= 0 )
    {
      v17 = UtilPathTail(*v16);
      *((_QWORD *)this + 12) = v17;
      if ( v17 )
      {
        v21 = OpenProcess(0x410u, 0, *(_DWORD *)this);
        tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 16, v21);
        v22 = (void *)*((_QWORD *)this + 2);
        if ( (unsigned __int64)v22 + 1 <= 1 )
        {
          v23 = GetLastError();
          v24 = ERROR_HR_FROM_WIN32(v23);
          v13 = v24;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, *(unsigned int *)this, v24);
          return v13;
        }
        v16 = (const unsigned __int16 **)((char *)this + 64);
        ProcessPathFromHandle = UtilGetProcessPathFromHandle(v22);
        v13 = ProcessPathFromHandle;
        if ( ProcessPathFromHandle < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 57;
            goto LABEL_9;
          }
          return v13;
        }
        v27 = UtilPathTail(*v16);
        *((_QWORD *)this + 13) = v27;
        if ( v27 )
          return 0;
        v13 = -2147024809;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v13;
        v20 = 58;
      }
      else
      {
        v13 = -2147024809;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v13;
        v20 = 55;
      }
      WPP_SF_S(v19[2], v20, v18, *v16);
      return v13;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 54;
      goto LABEL_9;
    }
  }
  else
  {
    v11 = GetLastError();
    ProcessPathFromHandle = ERROR_HR_FROM_WIN32(v11);
    v13 = ProcessPathFromHandle;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 53;
LABEL_9:
      WPP_SF_d(v14[2], v15, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, (unsigned int)ProcessPathFromHandle);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800111c0  push    rbx
0x1800111c2  push    rsi
0x1800111c3  push    rdi
0x1800111c4  push    r14
0x1800111c6  sub     rsp, 38h
0x1800111ca  mov     [rcx], edx
0x1800111cc  lea     rbx, [rcx+18h]
0x1800111d0  mov     [rcx+8], r8d
0x1800111d4  mov     rdi, rcx
0x1800111d7  mov     [rcx+4], r9d
0x1800111db  mov     r8d, r9d; dwProcessId
0x1800111de  xor     edx, edx; bInheritHandle
0x1800111e0  mov     ecx, 410h; dwDesiredAccess
0x1800111e5  call    cs:__imp_OpenProcess
0x1800111eb  mov     rdx, rax
0x1800111ee  mov     rcx, rbx
0x1800111f1  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800111f6  mov     rcx, [rbx]; hProcess
0x1800111f9  lea     r14, WPP_GLOBAL_Control
0x180011200  lea     rax, [rcx+1]
0x180011204  cmp     rax, 1
0x180011208  ja      loc_1800112B4
0x18001120e  call    cs:__imp_GetLastError
0x180011214  mov     ecx, eax; unsigned int
0x180011216  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001121b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011222  cmp     rcx, r14
0x180011225  jz      short loc_180011245
0x180011227  test    byte ptr [rcx+1Ch], 1
0x18001122b  jz      short loc_180011245
0x18001122d  mov     rcx, [rcx+10h]
0x180011231  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180011238  mov     edx, 34h ; '4'
0x18001123d  mov     r9d, eax
0x180011240  call    WPP_SF_d
0x180011245  mov     r8d, [rdi+4]; dwProcessId
0x180011249  xor     edx, edx; bInheritHandle
0x18001124b  mov     ecx, 1000h; dwDesiredAccess
0x180011250  call    cs:__imp_OpenProcess
0x180011256  mov     rdx, rax
0x180011259  mov     rcx, rbx
0x18001125c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180011261  mov     rcx, [rbx]
0x180011264  lea     rax, [rcx+1]
0x180011268  cmp     rax, 1
0x18001126c  ja      short loc_1800112B4
0x18001126e  call    cs:__imp_GetLastError
0x180011274  mov     ecx, eax; unsigned int
0x180011276  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001127b  mov     ebx, eax
0x18001127d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011284  cmp     rcx, r14
0x180011287  jz      loc_1800113E8
0x18001128d  test    byte ptr [rcx+1Ch], 1
0x180011291  jz      loc_1800113E8
0x180011297  mov     edx, 35h ; '5'
0x18001129c  mov     rcx, [rcx+10h]
0x1800112a0  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x1800112a7  mov     r9d, eax
0x1800112aa  call    WPP_SF_d
0x1800112af  jmp     loc_1800113E8
0x1800112b4  lea     rsi, [rdi+20h]
0x1800112b8  mov     rdx, rsi
0x1800112bb  call    ?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilGetProcessPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800112c0  mov     ebx, eax
0x1800112c2  test    eax, eax
0x1800112c4  jns     short loc_1800112E7
0x1800112c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112cd  cmp     rcx, r14
0x1800112d0  jz      loc_1800113E8
0x1800112d6  test    byte ptr [rcx+1Ch], 1
0x1800112da  jz      loc_1800113E8
0x1800112e0  mov     edx, 36h ; '6'
0x1800112e5  jmp     short loc_18001129C
0x1800112e7  mov     rcx, [rsi]; unsigned __int16 *
0x1800112ea  call    ?UtilPathTail@@YAPEBGPEBG@Z; UtilPathTail(ushort const *)
0x1800112ef  mov     [rdi+60h], rax
0x1800112f3  test    rax, rax
0x1800112f6  jnz     short loc_18001132B
0x1800112f8  mov     ebx, 80070057h
0x1800112fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011304  cmp     rcx, r14
0x180011307  jz      loc_1800113E8
0x18001130d  test    byte ptr [rcx+1Ch], 1
0x180011311  jz      loc_1800113E8
0x180011317  lea     edx, [rax+37h]
0x18001131a  mov     r9, [rsi]
0x18001131d  mov     rcx, [rcx+10h]
0x180011321  call    WPP_SF_S
0x180011326  jmp     loc_1800113E8
0x18001132b  mov     r8d, [rdi]; dwProcessId
0x18001132e  xor     edx, edx; bInheritHandle
0x180011330  mov     ecx, 410h; dwDesiredAccess
0x180011335  call    cs:__imp_OpenProcess
0x18001133b  mov     rdx, rax
0x18001133e  lea     rcx, [rdi+10h]
0x180011342  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180011347  mov     rcx, [rdi+10h]; hProcess
0x18001134b  lea     rax, [rcx+1]
0x18001134f  cmp     rax, 1
0x180011353  ja      short loc_180011388
0x180011355  call    cs:__imp_GetLastError
0x18001135b  mov     ecx, eax; unsigned int
0x18001135d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180011362  mov     ebx, eax
0x180011364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001136b  cmp     rcx, r14
0x18001136e  jz      short loc_1800113E8
0x180011370  test    byte ptr [rcx+1Ch], 1
0x180011374  jz      short loc_1800113E8
0x180011376  mov     r9d, [rdi]
0x180011379  mov     rcx, [rcx+10h]
0x18001137d  mov     [rsp+58h+var_38], eax
0x180011381  call    WPP_SF_dD
0x180011386  jmp     short loc_1800113E8
0x180011388  lea     rsi, [rdi+40h]
0x18001138c  mov     rdx, rsi
0x18001138f  call    ?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilGetProcessPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180011394  mov     ebx, eax
0x180011396  test    eax, eax
0x180011398  jns     short loc_1800113B6
0x18001139a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113a1  cmp     rcx, r14
0x1800113a4  jz      short loc_1800113E8
0x1800113a6  test    byte ptr [rcx+1Ch], 1
0x1800113aa  jz      short loc_1800113E8
0x1800113ac  mov     edx, 39h ; '9'
0x1800113b1  jmp     loc_18001129C
0x1800113b6  mov     rcx, [rsi]; unsigned __int16 *
0x1800113b9  call    ?UtilPathTail@@YAPEBGPEBG@Z; UtilPathTail(ushort const *)
0x1800113be  mov     [rdi+68h], rax
0x1800113c2  test    rax, rax
0x1800113c5  jnz     short loc_1800113E6
0x1800113c7  mov     ebx, 80070057h
0x1800113cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113d3  cmp     rcx, r14
0x1800113d6  jz      short loc_1800113E8
0x1800113d8  test    byte ptr [rcx+1Ch], 1
0x1800113dc  jz      short loc_1800113E8
0x1800113de  lea     edx, [rax+3Ah]
0x1800113e1  jmp     loc_18001131A
0x1800113e6  xor     ebx, ebx
0x1800113e8  mov     eax, ebx
0x1800113ea  add     rsp, 38h
0x1800113ee  pop     r14
0x1800113f0  pop     rdi
0x1800113f1  pop     rsi
0x1800113f2  pop     rbx
0x1800113f3  retn
```
