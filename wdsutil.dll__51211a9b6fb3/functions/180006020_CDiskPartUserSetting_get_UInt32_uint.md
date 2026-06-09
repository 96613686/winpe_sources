# CDiskPartUserSetting::get_UInt32(uint *)

- ea: `0x180006020`
- end: `0x180006352`
- name: `?get_UInt32@CDiskPartUserSetting@@UEAAJPEAI@Z`
- size: `818`
- prototype: `__int64 __fastcall(CDiskPartUserSetting *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180004d60`
- `0x180005360`
- `0x1800056a0`
- `0x1800056f0`
- `0x180005840`
- `0x1800058e0`
- `0x180006020`
- `0x180008c78`
- `0x180008d5c`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006316`
- `KERNEL32!GetLastError` at `0x180006316`
- `KERNEL32!HeapFree` at `0x180006137`
- `KERNEL32!HeapFree` at `0x180006269`
- `KERNEL32!HeapFree` at `0x180006137`
- `KERNEL32!HeapFree` at `0x180006269`
- `KERNEL32!GetProcessHeap` at `0x180006123`
- `KERNEL32!GetProcessHeap` at `0x180006255`
- `KERNEL32!GetProcessHeap` at `0x180006123`
- `KERNEL32!GetProcessHeap` at `0x180006255`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800061ba`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800061ba`
- `KERNEL32!SetLastError` at `0x180006167`
- `KERNEL32!SetLastError` at `0x18000627c`
- `KERNEL32!SetLastError` at `0x180006167`
- `KERNEL32!SetLastError` at `0x18000627c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall CDiskPartUserSetting::get_UInt32(CDiskPartUserSetting *this, unsigned int *a2)
{
  int UInt32; // esi
  unsigned __int16 v4; // bx
  unsigned __int64 v5; // r12
  __int64 DriveLayout; // rax
  void *v7; // rdi
  __int64 i; // rcx
  int v9; // r14d
  int v10; // r15d
  HANDLE ProcessHeap; // rax
  signed int result; // eax
  int v13; // esi
  unsigned __int64 v14; // r15
  unsigned int v15; // r14d
  _DWORD *v16; // rdi
  unsigned int j; // ecx
  int v18; // ebx
  HANDLE v19; // rax
  unsigned int v20; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  void **v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+38h] [rbp-C8h]
  void **v24; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  v26 = -2;
  if ( !(unsigned int)CUpgradeUserSetting::IsUpgrade() )
  {
    v25 = 0;
    v24 = &CDiskNumUserSetting::`vftable';
    v23 = 0;
    v22 = &CPartOffsetUserSetting::`vftable';
    v20 = -1;
    v21 = 0;
    UInt32 = CUInt32UserSetting::Simple_get_UInt32((CUInt32UserSetting *)&v24, &v20);
    if ( UInt32 < 0 )
      goto LABEL_19;
    UInt32 = CUInt64UserSetting::Simple_get_UInt64((CUInt64UserSetting *)&v22, &v21);
    if ( UInt32 < 0 )
      goto LABEL_19;
    v4 = v20;
    if ( (v20 & 0x80000000) == 0 && (v5 = v21) != 0 )
    {
      DriveLayout = GetDriveLayout(v20);
      v7 = (void *)DriveLayout;
      if ( DriveLayout )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          LOWORD(v9) = 0;
          v10 = 0;
          if ( (unsigned int)i >= *(_DWORD *)(DriveLayout + 4) )
            break;
          v9 = *(_DWORD *)(DriveLayout + 144 * i + 72);
          if ( v9 && v5 == *(_QWORD *)(DriveLayout + 144 * i + 56) )
          {
            v10 = 1;
            break;
          }
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
      }
      else
      {
        LOWORD(v9) = 0;
        v10 = 0;
      }
      if ( v10 )
      {
        *a2 = (unsigned __int16)v9 | (v4 << 16);
LABEL_19:
        v22 = &CStringUserSetting::`vftable';
        CUserSetting::~CUserSetting((CUserSetting *)&v22);
        v24 = &CStringUserSetting::`vftable';
        CUserSetting::~CUserSetting((CUserSetting *)&v24);
        return UInt32;
      }
    }
    else
    {
      SetLastError(0x57u);
    }
    *a2 = v4 << 16;
    goto LABEL_19;
  }
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    goto LABEL_37;
  if ( !Buffer[0] )
    goto LABEL_37;
  v20 = -1;
  v21 = 0;
  if ( !(unsigned int)GetDiskAndOffsetFromDriveLetter(Buffer[0], &v20, &v21) )
    goto LABEL_37;
  LOWORD(v13) = -1;
  v14 = v21;
  v15 = v20;
  if ( (v20 & 0x80000000) != 0 || !v21 )
  {
    SetLastError(0x57u);
    goto LABEL_34;
  }
  v16 = (_DWORD *)GetDriveLayout(v20);
  if ( !v16 )
  {
LABEL_34:
    v18 = 0;
    goto LABEL_35;
  }
  for ( j = 0; ; ++j )
  {
    LOWORD(v13) = -1;
    v18 = 0;
    if ( j >= v16[1] )
      break;
    v13 = v16[36 * j + 18];
    if ( v13 && v14 == *(_QWORD *)&v16[36 * j + 14] )
    {
      v18 = 1;
      break;
    }
  }
  v19 = GetProcessHeap();
  HeapFree(v19, 0, v16);
LABEL_35:
  if ( v18 )
  {
    v23 = 0;
    v22 = &CDiskNumUserSetting::`vftable';
    v25 = 0;
    v24 = &CPartOffsetUserSetting::`vftable';
    CUInt32UserSetting::SerializeUInt32((CUInt32UserSetting *)&v22, v15);
    CUInt64UserSetting::SerializeUInt64((CUInt64UserSetting *)&v24, v14);
    *a2 = (unsigned __int16)v13 | ((unsigned __int16)v15 << 16);
    v24 = &CStringUserSetting::`vftable';
    CUserSetting::~CUserSetting((CUserSetting *)&v24);
    v22 = &CStringUserSetting::`vftable';
    CUserSetting::~CUserSetting((CUserSetting *)&v22);
    return 0;
  }
LABEL_37:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180006020  push    rbp
0x180006022  push    rbx
0x180006023  push    rsi
0x180006024  push    rdi
0x180006025  push    r12
0x180006027  push    r13
0x180006029  push    r14
0x18000602b  push    r15
0x18000602d  lea     rbp, [rsp-1A8h]
0x180006035  sub     rsp, 2A8h
0x18000603c  mov     [rsp+2E0h+var_270], 0FFFFFFFFFFFFFFFEh
0x180006045  mov     rax, cs:__security_cookie
0x18000604c  xor     rax, rsp
0x18000604f  mov     [rbp+1E0h+var_50], rax
0x180006056  mov     r13, rdx
0x180006059  call    ?IsUpgrade@CUpgradeUserSetting@@SAHXZ; CUpgradeUserSetting::IsUpgrade(void)
0x18000605e  xor     r12d, r12d
0x180006061  test    eax, eax
0x180006063  jnz     loc_1800061B1
0x180006069  xorps   xmm0, xmm0
0x18000606c  movdqu  [rsp+2E0h+var_288], xmm0
0x180006072  lea     rax, ??_7CDiskNumUserSetting@@6B@; const CDiskNumUserSetting::`vftable'
0x180006079  mov     [rsp+2E0h+var_290], rax
0x18000607e  movdqu  [rsp+2E0h+var_2A8], xmm0
0x180006084  lea     rax, ??_7CPartOffsetUserSetting@@6B@; const CPartOffsetUserSetting::`vftable'
0x18000608b  mov     [rsp+2E0h+var_2B0], rax
0x180006090  mov     [rsp+2E0h+var_2C0], 0FFFFFFFFh
0x180006098  mov     [rsp+2E0h+var_2B8], r12
0x18000609d  lea     rdx, [rsp+2E0h+var_2C0]; unsigned int *
0x1800060a2  lea     rcx, [rsp+2E0h+var_290]; this
0x1800060a7  call    ?Simple_get_UInt32@CUInt32UserSetting@@IEAAJPEAI@Z; CUInt32UserSetting::Simple_get_UInt32(uint *)
0x1800060ac  mov     esi, eax
0x1800060ae  test    eax, eax
0x1800060b0  js      loc_18000617D
0x1800060b6  lea     rdx, [rsp+2E0h+var_2B8]; unsigned __int64 *
0x1800060bb  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800060c0  call    ?Simple_get_UInt64@CUInt64UserSetting@@IEAAJPEA_K@Z; CUInt64UserSetting::Simple_get_UInt64(unsigned __int64 *)
0x1800060c5  mov     esi, eax
0x1800060c7  test    eax, eax
0x1800060c9  js      loc_18000617D
0x1800060cf  mov     ebx, [rsp+2E0h+var_2C0]
0x1800060d3  test    ebx, ebx
0x1800060d5  js      loc_180006162
0x1800060db  mov     r12, [rsp+2E0h+var_2B8]
0x1800060e0  test    r12, r12
0x1800060e3  jz      short loc_180006162
0x1800060e5  mov     ecx, ebx
0x1800060e7  call    GetDriveLayout
0x1800060ec  mov     rdi, rax
0x1800060ef  test    rax, rax
0x1800060f2  jz      short loc_180006145
0x1800060f4  xor     ecx, ecx
0x1800060f6  xor     r14d, r14d
0x1800060f9  xor     r15d, r15d
0x1800060fc  cmp     ecx, [rax+4]
0x1800060ff  jnb     short loc_180006123
0x180006101  lea     rdx, [rcx+rcx*8]
0x180006105  add     rdx, rdx
0x180006108  mov     r14d, [rax+rdx*8+48h]
0x18000610d  test    r14d, r14d
0x180006110  jz      short loc_180006119
0x180006112  cmp     r12, [rax+rdx*8+38h]
0x180006117  jz      short loc_18000611D
0x180006119  inc     ecx
0x18000611b  jmp     short loc_1800060F6
0x18000611d  mov     r15d, 1
0x180006123  call    cs:__imp_GetProcessHeap
0x18000612a  nop     dword ptr [rax+rax+00h]
0x18000612f  mov     rcx, rax; hHeap
0x180006132  mov     r8, rdi; lpMem
0x180006135  xor     edx, edx; dwFlags
0x180006137  call    cs:__imp_HeapFree
0x18000613e  nop     dword ptr [rax+rax+00h]
0x180006143  jmp     short loc_18000614B
0x180006145  xor     r14d, r14d
0x180006148  xor     r15d, r15d
0x18000614b  test    r15d, r15d
0x18000614e  jz      short loc_180006173
0x180006150  movzx   ecx, bx
0x180006153  shl     ecx, 10h
0x180006156  movzx   eax, r14w
0x18000615a  or      ecx, eax
0x18000615c  mov     [r13+0], ecx
0x180006160  jmp     short loc_18000617D
0x180006162  mov     ecx, 57h ; 'W'; dwErrCode
0x180006167  call    cs:__imp_SetLastError
0x18000616e  nop     dword ptr [rax+rax+00h]
0x180006173  movzx   eax, bx
0x180006176  shl     eax, 10h
0x180006179  mov     [r13+0], eax
0x18000617d  lea     rax, ??_7CStringUserSetting@@6B@; const CStringUserSetting::`vftable'
0x180006184  mov     [rsp+2E0h+var_2B0], rax
0x180006189  lea     rcx, [rsp+2E0h+var_2B0]; this
0x18000618e  call    ??1CUserSetting@@QEAA@XZ; CUserSetting::~CUserSetting(void)
0x180006193  nop
0x180006194  lea     rax, ??_7CStringUserSetting@@6B@; const CStringUserSetting::`vftable'
0x18000619b  mov     [rsp+2E0h+var_290], rax
0x1800061a0  lea     rcx, [rsp+2E0h+var_290]; this
0x1800061a5  call    ??1CUserSetting@@QEAA@XZ; CUserSetting::~CUserSetting(void)
0x1800061aa  mov     eax, esi
0x1800061ac  jmp     loc_18000632E
0x1800061b1  mov     edx, 104h; uSize
0x1800061b6  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x1800061ba  call    cs:__imp_GetWindowsDirectoryW
0x1800061c1  nop     dword ptr [rax+rax+00h]
0x1800061c6  test    eax, eax
0x1800061c8  jz      loc_180006316
0x1800061ce  movzx   ecx, [rbp+1E0h+Buffer]
0x1800061d2  test    cx, cx
0x1800061d5  jz      loc_180006316
0x1800061db  mov     [rsp+2E0h+var_2C0], 0FFFFFFFFh
0x1800061e3  mov     [rsp+2E0h+var_2B8], r12
0x1800061e8  lea     r8, [rsp+2E0h+var_2B8]
0x1800061ed  lea     rdx, [rsp+2E0h+var_2C0]
0x1800061f2  call    GetDiskAndOffsetFromDriveLetter
0x1800061f7  test    eax, eax
0x1800061f9  jz      loc_180006316
0x1800061ff  or      esi, 0FFFFFFFFh
0x180006202  mov     r15, [rsp+2E0h+var_2B8]
0x180006207  mov     r14d, [rsp+2E0h+var_2C0]
0x18000620c  test    r14d, r14d
0x18000620f  js      short loc_180006277
0x180006211  test    r15, r15
0x180006214  jz      short loc_180006277
0x180006216  mov     ecx, r14d
0x180006219  call    GetDriveLayout
0x18000621e  mov     rdi, rax
0x180006221  test    rax, rax
0x180006224  jz      short loc_180006288
0x180006226  mov     ecx, r12d
0x180006229  or      esi, 0FFFFFFFFh
0x18000622c  mov     ebx, r12d
0x18000622f  cmp     ecx, [rdi+4]
0x180006232  jnb     short loc_180006255
0x180006234  mov     eax, ecx
0x180006236  lea     rdx, [rax+rax*8]
0x18000623a  add     rdx, rdx
0x18000623d  mov     esi, [rdi+rdx*8+48h]
0x180006241  test    esi, esi
0x180006243  jz      short loc_18000624C
0x180006245  cmp     r15, [rdi+rdx*8+38h]
0x18000624a  jz      short loc_180006250
0x18000624c  inc     ecx
0x18000624e  jmp     short loc_180006229
0x180006250  mov     ebx, 1
0x180006255  call    cs:__imp_GetProcessHeap
0x18000625c  nop     dword ptr [rax+rax+00h]
0x180006261  mov     rcx, rax; hHeap
0x180006264  mov     r8, rdi; lpMem
0x180006267  xor     edx, edx; dwFlags
0x180006269  call    cs:__imp_HeapFree
0x180006270  nop     dword ptr [rax+rax+00h]
0x180006275  jmp     short loc_18000628B
0x180006277  mov     ecx, 57h ; 'W'; dwErrCode
0x18000627c  call    cs:__imp_SetLastError
0x180006283  nop     dword ptr [rax+rax+00h]
0x180006288  mov     ebx, r12d
0x18000628b  test    ebx, ebx
0x18000628d  jz      loc_180006316
0x180006293  xorps   xmm0, xmm0
0x180006296  movdqu  [rsp+2E0h+var_2A8], xmm0
0x18000629c  lea     rax, ??_7CDiskNumUserSetting@@6B@; const CDiskNumUserSetting::`vftable'
0x1800062a3  mov     [rsp+2E0h+var_2B0], rax
0x1800062a8  movdqu  [rsp+2E0h+var_288], xmm0
0x1800062ae  lea     rax, ??_7CPartOffsetUserSetting@@6B@; const CPartOffsetUserSetting::`vftable'
0x1800062b5  mov     [rsp+2E0h+var_290], rax
0x1800062ba  mov     edx, r14d; unsigned int
0x1800062bd  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800062c2  call    ?SerializeUInt32@CUInt32UserSetting@@IEAAXI@Z; CUInt32UserSetting::SerializeUInt32(uint)
0x1800062c7  mov     rdx, r15; unsigned __int64
0x1800062ca  lea     rcx, [rsp+2E0h+var_290]; this
0x1800062cf  call    ?SerializeUInt64@CUInt64UserSetting@@IEAAX_K@Z; CUInt64UserSetting::SerializeUInt64(unsigned __int64)
0x1800062d4  movzx   ecx, r14w
0x1800062d8  shl     ecx, 10h
0x1800062db  movzx   eax, si
0x1800062de  or      ecx, eax
0x1800062e0  mov     [r13+0], ecx
0x1800062e4  lea     rax, ??_7CStringUserSetting@@6B@; const CStringUserSetting::`vftable'
0x1800062eb  mov     [rsp+2E0h+var_290], rax
0x1800062f0  lea     rcx, [rsp+2E0h+var_290]; this
0x1800062f5  call    ??1CUserSetting@@QEAA@XZ; CUserSetting::~CUserSetting(void)
0x1800062fa  nop
0x1800062fb  lea     rax, ??_7CStringUserSetting@@6B@; const CStringUserSetting::`vftable'
0x180006302  mov     [rsp+2E0h+var_2B0], rax
0x180006307  lea     rcx, [rsp+2E0h+var_2B0]; this
0x18000630c  call    ??1CUserSetting@@QEAA@XZ; CUserSetting::~CUserSetting(void)
0x180006311  mov     eax, r12d
0x180006314  jmp     short loc_18000632E
0x180006316  call    cs:__imp_GetLastError
0x18000631d  nop     dword ptr [rax+rax+00h]
0x180006322  test    eax, eax
0x180006324  jle     short loc_18000632E
0x180006326  movzx   eax, ax
0x180006329  or      eax, 80070000h
0x18000632e  mov     rcx, [rbp+1E0h+var_50]
0x180006335  xor     rcx, rsp; StackCookie
0x180006338  call    __security_check_cookie
0x18000633d  add     rsp, 2A8h
0x180006344  pop     r15
0x180006346  pop     r14
0x180006348  pop     r13
0x18000634a  pop     r12
0x18000634c  pop     rdi
0x18000634d  pop     rsi
0x18000634e  pop     rbx
0x18000634f  pop     rbp
0x180006350  retn
```
