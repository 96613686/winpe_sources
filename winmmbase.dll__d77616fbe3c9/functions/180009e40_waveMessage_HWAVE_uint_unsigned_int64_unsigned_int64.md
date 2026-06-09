# waveMessage(HWAVE__ *,uint,unsigned __int64,unsigned __int64)

- ea: `0x180009e40`
- end: `0x18000a0d2`
- name: `?waveMessage@@YAIPEAUHWAVE__@@I_K1@Z`
- size: `658`
- prototype: `unsigned int __fastcall(HWAVE, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180007640`
- `0x180008530`
- `0x180009760`
- `0x180009de0`
- `0x18000a790`
- `0x18000ec90`
- `0x18000ed70`
- `0x18000eff0`
- `0x18001d6f0`
- `0x18001d750`
- `0x18001d7a0`
- `0x18001d7f0`
- `0x18001d890`
- `0x18001d8f0`
- `0x18001d950`
- `0x18001d9a0`
- `0x18001d9f0`
- `0x18001da40`
- `0x18001da90`

## callees

- `0x180009e40`
- `0x180012d08`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009fe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a06a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009fe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a06a`

## pseudocode

```c
__int64 __fastcall waveMessage(HWAVE a1, unsigned int a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v9; // ecx
  unsigned __int64 v10; // rax
  int v11; // r12d
  unsigned int v12; // ebx
  HWAVE v13; // rsi
  _QWORD *j; // rax
  BOOL v15; // eax
  HWAVE v17; // rsi
  _QWORD *i; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 - 10);
  EnterCriticalSection((LPCRITICAL_SECTION)a1 - 1);
  v9 = *((_DWORD *)a1 - 17);
  if ( (v9 & 1) != 0 )
  {
    LeaveCriticalSection(v4);
    return 6;
  }
  else
  {
    if ( (v9 & 2) == 0 )
    {
      if ( (unsigned __int64)a1 < 0x10000 )
      {
        v11 = 0;
      }
      else
      {
        if ( (((unsigned __int64)a1 + 1) & 0xFFFFFFFEFFFFFFFFuLL) == 0 )
          goto LABEL_8;
        v10 = gdwMinVirtualAddress;
        if ( (unsigned __int64)a1 > gdwMaxVirtualAddress || (unsigned __int64)a1 < gdwMinVirtualAddress )
        {
          v11 = 0;
LABEL_7:
          if ( (unsigned __int64)a1 <= gdwMaxVirtualAddress && (unsigned __int64)a1 >= v10 )
          {
            v17 = a1 - 20;
            EnterCriticalSection(&HandleListCritSec);
            for ( i = (_QWORD *)pHandleList; i; i = (_QWORD *)*i )
            {
              if ( i == (_QWORD *)v17 )
              {
                LeaveCriticalSection(&HandleListCritSec);
                LOBYTE(v11) = *((_DWORD *)v17 + 2) == 2;
                goto LABEL_28;
              }
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            {
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
            }
            LeaveCriticalSection(&HandleListCritSec);
LABEL_28:
            if ( v11 )
            {
LABEL_16:
              v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)a1 + 80LL))(
                      *((unsigned int *)a1 + 2),
                      a2,
                      *((_QWORD *)a1 + 2),
                      a3,
                      a4);
              goto LABEL_17;
            }
          }
LABEL_8:
          v12 = 5;
LABEL_17:
          LeaveCriticalSection(v4);
          return v12;
        }
        v13 = a1 - 20;
        EnterCriticalSection(&HandleListCritSec);
        for ( j = (_QWORD *)pHandleList; j; j = (_QWORD *)*j )
        {
          if ( j == (_QWORD *)v13 )
          {
            LeaveCriticalSection(&HandleListCritSec);
            v11 = 0;
            v15 = *((_DWORD *)v13 + 2) == 1;
            goto LABEL_15;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
        }
        LeaveCriticalSection(&HandleListCritSec);
        v11 = 0;
        v15 = 0;
LABEL_15:
        if ( v15 )
          goto LABEL_16;
      }
      if ( (unsigned __int64)a1 < 0x10000 || a1 == (HWAVE)-1LL || a1 == (HWAVE)0xFFFFFFFFLL )
        goto LABEL_8;
      v10 = gdwMinVirtualAddress;
      goto LABEL_7;
    }
    LeaveCriticalSection(v4);
    return 12;
  }
}

```

## disassembly

```asm
0x180009e40  push    rbx
0x180009e42  push    rbp
0x180009e43  push    rdi
0x180009e44  push    r14
0x180009e46  push    r15
0x180009e48  sub     rsp, 30h
0x180009e4c  lea     rdi, [rcx-28h]
0x180009e50  mov     rbx, rcx
0x180009e53  mov     rcx, rdi; lpCriticalSection
0x180009e56  mov     rbp, r9
0x180009e59  mov     r14, r8
0x180009e5c  mov     r15d, edx
0x180009e5f  call    cs:__imp_EnterCriticalSection
0x180009e65  mov     ecx, [rbx-44h]
0x180009e68  test    cl, 1
0x180009e6b  jnz     loc_180009F76
0x180009e71  test    cl, 2
0x180009e74  jnz     loc_180009F90
0x180009e7a  mov     [rsp+58h+arg_0], rsi
0x180009e7f  mov     [rsp+58h+arg_8], r12
0x180009e84  mov     [rsp+58h+arg_10], r13
0x180009e89  cmp     rbx, 10000h
0x180009e90  jb      loc_18000A01C
0x180009e96  lea     rax, [rbx+1]
0x180009e9a  mov     rcx, 0FFFFFFFEFFFFFFFFh
0x180009ea4  test    rcx, rax
0x180009ea7  jz      short loc_180009ED0
0x180009ea9  cmp     rbx, cs:gdwMaxVirtualAddress
0x180009eb0  mov     rax, cs:gdwMinVirtualAddress
0x180009eb7  jbe     short loc_180009ED7
0x180009eb9  xor     r12d, r12d
0x180009ebc  lea     r13, WPP_GLOBAL_Control
0x180009ec3  cmp     rbx, cs:gdwMaxVirtualAddress
0x180009eca  jbe     loc_180009FAA
0x180009ed0  mov     ebx, 5
0x180009ed5  jmp     short loc_180009F50
0x180009ed7  cmp     rbx, rax
0x180009eda  jb      short loc_180009EB9
0x180009edc  lea     rcx, HandleListCritSec; lpCriticalSection
0x180009ee3  lea     rsi, [rbx-50h]
0x180009ee7  call    cs:__imp_EnterCriticalSection
0x180009eed  mov     rax, cs:pHandleList
0x180009ef4  lea     r13, WPP_GLOBAL_Control
0x180009efb  test    rax, rax
0x180009efe  jz      loc_18000A057
0x180009f04  cmp     rax, rsi
0x180009f07  jz      short loc_180009F0E
0x180009f09  mov     rax, [rax]
0x180009f0c  jmp     short loc_180009EF4
0x180009f0e  lea     rcx, HandleListCritSec; lpCriticalSection
0x180009f15  call    cs:__imp_LeaveCriticalSection
0x180009f1b  xor     r12d, r12d
0x180009f1e  cmp     dword ptr [rsi+8], 1
0x180009f22  mov     eax, r12d
0x180009f25  setz    al
0x180009f28  test    eax, eax
0x180009f2a  jz      loc_18000A026
0x180009f30  mov     rax, [rbx]
0x180009f33  mov     r9, r14
0x180009f36  mov     r8, [rbx+10h]
0x180009f3a  mov     edx, r15d
0x180009f3d  mov     ecx, [rbx+8]
0x180009f40  mov     [rsp+58h+var_38], rbp
0x180009f45  mov     rax, [rax+50h]
0x180009f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f4e  mov     ebx, eax
0x180009f50  mov     rcx, rdi; lpCriticalSection
0x180009f53  call    cs:__imp_LeaveCriticalSection
0x180009f59  mov     r13, [rsp+58h+arg_10]
0x180009f5e  mov     eax, ebx
0x180009f60  mov     r12, [rsp+58h+arg_8]
0x180009f65  mov     rsi, [rsp+58h+arg_0]
0x180009f6a  add     rsp, 30h
0x180009f6e  pop     r15
0x180009f70  pop     r14
0x180009f72  pop     rdi
0x180009f73  pop     rbp
0x180009f74  pop     rbx
0x180009f75  retn
0x180009f76  mov     rcx, rdi; lpCriticalSection
0x180009f79  call    cs:__imp_LeaveCriticalSection
0x180009f7f  mov     eax, 6
0x180009f84  add     rsp, 30h
0x180009f88  pop     r15
0x180009f8a  pop     r14
0x180009f8c  pop     rdi
0x180009f8d  pop     rbp
0x180009f8e  pop     rbx
0x180009f8f  retn
0x180009f90  mov     rcx, rdi; lpCriticalSection
0x180009f93  call    cs:__imp_LeaveCriticalSection
0x180009f99  mov     eax, 0Ch
0x180009f9e  add     rsp, 30h
0x180009fa2  pop     r15
0x180009fa4  pop     r14
0x180009fa6  pop     rdi
0x180009fa7  pop     rbp
0x180009fa8  pop     rbx
0x180009fa9  retn
0x180009faa  cmp     rbx, rax
0x180009fad  jb      loc_180009ED0
0x180009fb3  lea     rcx, HandleListCritSec; lpCriticalSection
0x180009fba  lea     rsi, [rbx-50h]
0x180009fbe  call    cs:__imp_EnterCriticalSection
0x180009fc4  mov     rax, cs:pHandleList
0x180009fcb  test    rax, rax
0x180009fce  jz      short loc_180009FF1
0x180009fd0  cmp     rax, rsi
0x180009fd3  jz      short loc_180009FDA
0x180009fd5  mov     rax, [rax]
0x180009fd8  jmp     short loc_180009FCB
0x180009fda  lea     rcx, HandleListCritSec; lpCriticalSection
0x180009fe1  call    cs:__imp_LeaveCriticalSection
0x180009fe7  cmp     dword ptr [rsi+8], 2
0x180009feb  setz    r12b
0x180009fef  jmp     short loc_18000A00E
0x180009ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ff8  cmp     rcx, r13
0x180009ffb  jnz     loc_18000A0A1
0x18000a001  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000a008  call    cs:__imp_LeaveCriticalSection
0x18000a00e  test    r12d, r12d
0x18000a011  jnz     loc_180009F30
0x18000a017  jmp     loc_180009ED0
0x18000a01c  xor     r12d, r12d
0x18000a01f  lea     r13, WPP_GLOBAL_Control
0x18000a026  cmp     rbx, 10000h
0x18000a02d  jb      loc_180009ED0
0x18000a033  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a037  jz      loc_180009ED0
0x18000a03d  mov     eax, 0FFFFFFFFh
0x18000a042  cmp     rbx, rax
0x18000a045  jz      loc_180009ED0
0x18000a04b  mov     rax, cs:gdwMinVirtualAddress
0x18000a052  jmp     loc_180009EC3
0x18000a057  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a05e  cmp     rcx, r13
0x18000a061  jnz     short loc_18000A07B
0x18000a063  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000a06a  call    cs:__imp_LeaveCriticalSection
0x18000a070  xor     r12d, r12d
0x18000a073  mov     eax, r12d
0x18000a076  jmp     loc_180009F28
0x18000a07b  test    dword ptr [rcx+1Ch], 400000h
0x18000a082  jz      short loc_18000A063
0x18000a084  cmp     byte ptr [rcx+19h], 1
0x18000a088  jb      short loc_18000A063
0x18000a08a  mov     rcx, [rcx+10h]
0x18000a08e  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000a095  mov     edx, 0Ah
0x18000a09a  call    WPP_SF_
0x18000a09f  jmp     short loc_18000A063
0x18000a0a1  test    dword ptr [rcx+1Ch], 400000h
0x18000a0a8  jz      loc_18000A001
0x18000a0ae  cmp     byte ptr [rcx+19h], 1
0x18000a0b2  jb      loc_18000A001
0x18000a0b8  mov     rcx, [rcx+10h]
0x18000a0bc  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000a0c3  mov     edx, 0Ah
0x18000a0c8  call    WPP_SF_
0x18000a0cd  jmp     loc_18000A001
```
