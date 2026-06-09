# LOG_WRITER::Write(STRU *)

- ea: `0x180006148`
- end: `0x1800062bd`
- name: `?Write@LOG_WRITER@@AEAAJPEAVSTRU@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800062c4`

## callees

- `0x180004b28`
- `0x180006148`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006280`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006197`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006197`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000619d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000619d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000628c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000628c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180006186`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180006186`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800061c5`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800061c5`
- `iisutil!?AppendWSimple@STRA@@QEAAJPEBGK@Z` at `0x1800061cd`
- `iisutil!?AppendWSimple@STRA@@QEAAJPEBGK@Z` at `0x1800061cd`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006214`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006214`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180006246`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18000626b`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180006246`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18000626b`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::Write(struct _RTL_CRITICAL_SECTION *this, struct STRU *a2)
{
  __int64 v4; // rax
  unsigned int v5; // r14d
  unsigned int v6; // r8d
  const unsigned __int16 *v7; // rdx
  int appended; // eax
  int v9; // ebx
  _BYTE v11[48]; // [rsp+20h] [rbp-268h] BYREF
  int v12; // [rsp+50h] [rbp-238h]
  char v13[512]; // [rsp+60h] [rbp-228h] BYREF

  STRA::STRA((STRA *)v11, v13, 0x200u);
  EnterCriticalSection(this + 17);
  this[16].LockSemaphore = (HANDLE)GetTickCount64();
  v4 = *(_QWORD *)&this->LockCount;
  v5 = *(_DWORD *)(v4 + 36);
  v6 = *((_DWORD *)a2 + 12);
  v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  if ( *(_DWORD *)(v4 + 12) )
    appended = STRA::CopyWToUTF8Unescaped((STRA *)v11, v7, v6);
  else
    appended = STRA::AppendWSimple((STRA *)v11, v7, v6);
  v9 = appended;
  if ( appended >= 0 )
  {
    if ( (unsigned int)(LODWORD(this[4].OwningThread) + v12 + 1) <= *((_DWORD *)g_pLogSvcAdmin + 3) )
    {
      if ( v5 && HIDWORD(this[15].OwningThread) + 1 >= v5 )
      {
        v9 = STRA::Append((STRA *)&this[3].LockCount, (const struct STRA *)v11);
        if ( v9 >= 0 )
          v9 = LOG_WRITER::Flush((LOG_WRITER *)this, 1);
      }
      else
      {
        v9 = STRA::Append((STRA *)&this[3].LockCount, (const struct STRA *)v11);
        if ( v9 >= 0 )
          ++HIDWORD(this[15].OwningThread);
      }
    }
    else
    {
      v9 = LOG_WRITER::Flush((LOG_WRITER *)this, 1);
      if ( v9 >= 0 )
      {
        v9 = STRA::Copy((STRA *)&this[3].LockCount, (const struct STRA *)v11);
        if ( v9 >= 0 )
          HIDWORD(this[15].OwningThread) = 1;
      }
    }
  }
  LeaveCriticalSection(this + 17);
  STRA::~STRA((STRA *)v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006148  mov     [rsp+arg_10], rbx
0x18000614d  mov     [rsp+arg_18], rbp
0x180006152  push    rdi
0x180006153  push    r14
0x180006155  push    r15
0x180006157  sub     rsp, 270h
0x18000615e  mov     rax, cs:__security_cookie
0x180006165  xor     rax, rsp
0x180006168  mov     [rsp+288h+var_28], rax
0x180006170  mov     rbx, rdx
0x180006173  mov     rdi, rcx
0x180006176  mov     r8d, 200h
0x18000617c  lea     rdx, [rsp+288h+var_228]
0x180006181  lea     rcx, [rsp+288h+var_268]
0x180006186  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000618c  nop
0x18000618d  lea     r15, [rdi+2A8h]
0x180006194  mov     rcx, r15; lpCriticalSection
0x180006197  call    cs:__imp_EnterCriticalSection
0x18000619d  call    cs:__imp_GetTickCount64
0x1800061a3  mov     [rdi+298h], rax
0x1800061aa  mov     rax, [rdi+8]
0x1800061ae  mov     r14d, [rax+24h]
0x1800061b2  mov     r8d, [rbx+30h]
0x1800061b6  mov     rdx, [rbx+20h]
0x1800061ba  lea     rcx, [rsp+288h+var_268]
0x1800061bf  cmp     dword ptr [rax+0Ch], 0
0x1800061c3  jz      short loc_1800061CD
0x1800061c5  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x1800061cb  jmp     short loc_1800061D3
0x1800061cd  call    cs:__imp_?AppendWSimple@STRA@@QEAAJPEBGK@Z; STRA::AppendWSimple(ushort const *,ulong)
0x1800061d3  mov     ebx, eax
0x1800061d5  test    eax, eax
0x1800061d7  js      loc_18000627D
0x1800061dd  lea     rbp, [rdi+80h]
0x1800061e4  mov     edx, [rsp+288h+var_238]
0x1800061e8  inc     edx
0x1800061ea  add     edx, [rbp+30h]
0x1800061ed  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x1800061f4  cmp     edx, [rax+0Ch]
0x1800061f7  jbe     short loc_18000622C
0x1800061f9  mov     edx, 1; int
0x1800061fe  mov     rcx, rdi; this
0x180006201  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x180006206  mov     ebx, eax
0x180006208  test    eax, eax
0x18000620a  js      short loc_18000627D
0x18000620c  lea     rdx, [rsp+288h+var_268]
0x180006211  mov     rcx, rbp
0x180006214  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000621a  mov     ebx, eax
0x18000621c  test    eax, eax
0x18000621e  js      short loc_18000627D
0x180006220  mov     dword ptr [rdi+26Ch], 1
0x18000622a  jmp     short loc_18000627D
0x18000622c  test    r14d, r14d
0x18000622f  jz      short loc_180006263
0x180006231  mov     eax, [rdi+26Ch]
0x180006237  inc     eax
0x180006239  cmp     eax, r14d
0x18000623c  jb      short loc_180006263
0x18000623e  lea     rdx, [rsp+288h+var_268]
0x180006243  mov     rcx, rbp
0x180006246  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18000624c  mov     ebx, eax
0x18000624e  test    eax, eax
0x180006250  js      short loc_18000627D
0x180006252  mov     edx, 1; int
0x180006257  mov     rcx, rdi; this
0x18000625a  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x18000625f  mov     ebx, eax
0x180006261  jmp     short loc_18000627D
0x180006263  lea     rdx, [rsp+288h+var_268]
0x180006268  mov     rcx, rbp
0x18000626b  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180006271  mov     ebx, eax
0x180006273  test    eax, eax
0x180006275  js      short loc_18000627D
0x180006277  inc     dword ptr [rdi+26Ch]
0x18000627d  mov     rcx, r15; lpCriticalSection
0x180006280  call    cs:__imp_LeaveCriticalSection
0x180006286  nop
0x180006287  lea     rcx, [rsp+288h+var_268]
0x18000628c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006292  mov     eax, ebx
0x180006294  mov     rcx, [rsp+288h+var_28]
0x18000629c  xor     rcx, rsp; StackCookie
0x18000629f  call    __security_check_cookie
0x1800062a4  lea     r11, [rsp+288h+var_18]
0x1800062ac  mov     rbx, [r11+30h]
0x1800062b0  mov     rbp, [r11+38h]
0x1800062b4  mov     rsp, r11
0x1800062b7  pop     r15
0x1800062b9  pop     r14
0x1800062bb  pop     rdi
0x1800062bc  retn
```
