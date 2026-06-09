# CJob::UpdateJobState(int)

- ea: `0x180023e5c`
- end: `0x180023f9c`
- name: `?UpdateJobState@CJob@@QEAAJH@Z`
- size: `320`
- prototype: `__int64 __fastcall(CJob *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011a98`
- `0x18001225c`
- `0x1800247dc`
- `0x18002580c`

## callees

- `0x180023e5c`
- `0x180025500`
- `0x18002b398`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180023ea4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180023ea4`

## pseudocode

```c
int __fastcall CJob::UpdateJobState(CJob *this, int a2)
{
  int result; // eax
  int v5; // ecx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned __int16 *v9; // [rsp+30h] [rbp-30h]
  unsigned __int16 v10; // [rsp+40h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  if ( (*((_DWORD *)this + 22) & 0x1000000) == 0 )
  {
    *((_DWORD *)this + 21) = 267013;
    return 0;
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  if ( a2 )
  {
    if ( ++SystemTime.wMinute >= 0x3Cu )
    {
      SystemTime.wMinute = 0;
      if ( ++SystemTime.wHour >= 0x18u )
      {
        SystemTime.wHour = 0;
        IncrementDay(&SystemTime);
      }
    }
  }
  v10 = 0;
  result = CJob::GetRunTimesP(this, &SystemTime, 0, &v10, 1u, 0, v9);
  v5 = result;
  if ( result >= 0 )
  {
    v6 = *((_DWORD *)this + 22);
    if ( v5 == 267015 )
    {
      v7 = v6 | 0x40000;
      *((_DWORD *)this + 21) = 267013;
      *((_DWORD *)this + 22) = v7;
    }
    else
    {
      v8 = v6 & 0xFFFBFFFF;
      if ( v10 || v5 == 267016 )
      {
        v7 = v8 & 0xFFBFFFFF;
        *((_DWORD *)this + 22) = v7;
        if ( !a2 && (v7 & 0x1000000) != 0 )
        {
          if ( *((_WORD *)this + 48) )
            *((_DWORD *)this + 21) = 267008;
          else
            *((_DWORD *)this + 21) = 267011;
        }
      }
      else
      {
        v7 = v8 | 0x400000;
        *((_DWORD *)this + 22) = v7;
      }
    }
    if ( (v7 & 4) != 0 )
      *((_DWORD *)this + 21) = 267010;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180023e5c  mov     [rsp-18h+arg_8], rbx
0x180023e61  mov     [rsp-18h+arg_10], rsi
0x180023e66  push    rbp
0x180023e67  push    rdi
0x180023e68  push    r14
0x180023e6a  mov     rbp, rsp
0x180023e6d  sub     rsp, 60h
0x180023e71  mov     rax, cs:__security_cookie
0x180023e78  xor     rax, rsp
0x180023e7b  mov     [rbp+var_8], rax
0x180023e7f  test    dword ptr [rcx+58h], 1000000h
0x180023e86  mov     edi, edx
0x180023e88  mov     rbx, rcx
0x180023e8b  jnz     short loc_180023E99
0x180023e8d  mov     dword ptr [rcx+54h], 41305h
0x180023e94  jmp     loc_180023F79
0x180023e99  xorps   xmm0, xmm0
0x180023e9c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180023ea0  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180023ea4  call    cs:__imp_GetLocalTime
0x180023eaa  xor     esi, esi
0x180023eac  lea     r14d, [rsi+1]
0x180023eb0  test    edi, edi
0x180023eb2  jz      short loc_180023EE9
0x180023eb4  movzx   eax, [rbp+SystemTime.wMinute]
0x180023eb8  add     ax, r14w
0x180023ebc  mov     [rbp+SystemTime.wMinute], ax
0x180023ec0  cmp     ax, 3Ch ; '<'
0x180023ec4  jb      short loc_180023EE9
0x180023ec6  movzx   ecx, [rbp+SystemTime.wHour]
0x180023eca  add     cx, r14w
0x180023ece  mov     [rbp+SystemTime.wMinute], si
0x180023ed2  mov     [rbp+SystemTime.wHour], cx
0x180023ed6  cmp     cx, 18h
0x180023eda  jb      short loc_180023EE9
0x180023edc  lea     rcx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180023ee0  mov     [rbp+SystemTime.wHour], si
0x180023ee4  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180023ee9  mov     [rsp+60h+var_38], rsi; struct CTimeRunList *
0x180023eee  lea     r9, [rbp+var_20]; unsigned __int16 *
0x180023ef2  xor     r8d, r8d; struct _SYSTEMTIME *
0x180023ef5  mov     [rsp+60h+var_40], r14w; unsigned __int16
0x180023efb  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180023eff  mov     [rbp+var_20], si
0x180023f03  mov     rcx, rbx; this
0x180023f06  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x180023f0b  mov     ecx, eax
0x180023f0d  test    eax, eax
0x180023f0f  js      short loc_180023F7B
0x180023f11  mov     eax, [rbx+58h]
0x180023f14  cmp     ecx, 41307h
0x180023f1a  jnz     short loc_180023F2C
0x180023f1c  bts     eax, 12h
0x180023f20  mov     dword ptr [rbx+54h], 41305h
0x180023f27  mov     [rbx+58h], eax
0x180023f2a  jmp     short loc_180023F6E
0x180023f2c  btr     eax, 12h
0x180023f30  cmp     [rbp+var_20], si
0x180023f34  jnz     short loc_180023F47
0x180023f36  cmp     ecx, 41308h
0x180023f3c  jz      short loc_180023F47
0x180023f3e  bts     eax, 16h
0x180023f42  mov     [rbx+58h], eax
0x180023f45  jmp     short loc_180023F6E
0x180023f47  btr     eax, 16h
0x180023f4b  mov     [rbx+58h], eax
0x180023f4e  test    edi, edi
0x180023f50  jnz     short loc_180023F6E
0x180023f52  bt      eax, 18h
0x180023f56  jnb     short loc_180023F6E
0x180023f58  cmp     [rbx+60h], si
0x180023f5c  jnz     short loc_180023F67
0x180023f5e  mov     dword ptr [rbx+54h], 41303h
0x180023f65  jmp     short loc_180023F6E
0x180023f67  mov     dword ptr [rbx+54h], 41300h
0x180023f6e  test    al, 4
0x180023f70  jz      short loc_180023F79
0x180023f72  mov     dword ptr [rbx+54h], 41302h
0x180023f79  xor     eax, eax
0x180023f7b  mov     rcx, [rbp+var_8]
0x180023f7f  xor     rcx, rsp; StackCookie
0x180023f82  call    __security_check_cookie
0x180023f87  lea     r11, [rsp+60h+var_s0]
0x180023f8c  mov     rbx, [r11+28h]
0x180023f90  mov     rsi, [r11+30h]
0x180023f94  mov     rsp, r11
0x180023f97  pop     r14
0x180023f99  pop     rdi
0x180023f9a  pop     rbp
0x180023f9b  retn
```
