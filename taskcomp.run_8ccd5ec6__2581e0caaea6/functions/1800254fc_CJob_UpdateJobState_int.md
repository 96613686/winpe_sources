# CJob::UpdateJobState(int)

- ea: `0x1800254fc`
- end: `0x180025643`
- name: `?UpdateJobState@CJob@@QEAAJH@Z`
- size: `327`
- prototype: `__int64 __fastcall(CJob *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180012594`
- `0x180012d8c`
- `0x180025ed4`
- `0x180026fec`

## callees

- `0x1800254fc`
- `0x180026cc8`
- `0x18002cfd4`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180025544`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180025544`

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
0x1800254fc  mov     [rsp-18h+arg_8], rbx
0x180025501  mov     [rsp-18h+arg_10], rsi
0x180025506  push    rbp
0x180025507  push    rdi
0x180025508  push    r14
0x18002550a  mov     rbp, rsp
0x18002550d  sub     rsp, 60h
0x180025511  mov     rax, cs:__security_cookie
0x180025518  xor     rax, rsp
0x18002551b  mov     [rbp+var_8], rax
0x18002551f  test    dword ptr [rcx+58h], 1000000h
0x180025526  mov     edi, edx
0x180025528  mov     rbx, rcx
0x18002552b  jnz     short loc_180025539
0x18002552d  mov     dword ptr [rcx+54h], 41305h
0x180025534  jmp     loc_18002561F
0x180025539  xorps   xmm0, xmm0
0x18002553c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180025540  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180025544  call    cs:__imp_GetLocalTime
0x18002554b  nop     dword ptr [rax+rax+00h]
0x180025550  xor     esi, esi
0x180025552  lea     r14d, [rsi+1]
0x180025556  test    edi, edi
0x180025558  jz      short loc_18002558F
0x18002555a  movzx   eax, [rbp+SystemTime.wMinute]
0x18002555e  add     ax, r14w
0x180025562  mov     [rbp+SystemTime.wMinute], ax
0x180025566  cmp     ax, 3Ch ; '<'
0x18002556a  jb      short loc_18002558F
0x18002556c  movzx   ecx, [rbp+SystemTime.wHour]
0x180025570  add     cx, r14w
0x180025574  mov     [rbp+SystemTime.wMinute], si
0x180025578  mov     [rbp+SystemTime.wHour], cx
0x18002557c  cmp     cx, 18h
0x180025580  jb      short loc_18002558F
0x180025582  lea     rcx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180025586  mov     [rbp+SystemTime.wHour], si
0x18002558a  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x18002558f  mov     [rsp+60h+var_38], rsi; struct CTimeRunList *
0x180025594  lea     r9, [rbp+var_20]; unsigned __int16 *
0x180025598  xor     r8d, r8d; struct _SYSTEMTIME *
0x18002559b  mov     [rsp+60h+var_40], r14w; unsigned __int16
0x1800255a1  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x1800255a5  mov     [rbp+var_20], si
0x1800255a9  mov     rcx, rbx; this
0x1800255ac  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x1800255b1  mov     ecx, eax
0x1800255b3  test    eax, eax
0x1800255b5  js      short loc_180025621
0x1800255b7  mov     eax, [rbx+58h]
0x1800255ba  cmp     ecx, 41307h
0x1800255c0  jnz     short loc_1800255D2
0x1800255c2  bts     eax, 12h
0x1800255c6  mov     dword ptr [rbx+54h], 41305h
0x1800255cd  mov     [rbx+58h], eax
0x1800255d0  jmp     short loc_180025614
0x1800255d2  btr     eax, 12h
0x1800255d6  cmp     [rbp+var_20], si
0x1800255da  jnz     short loc_1800255ED
0x1800255dc  cmp     ecx, 41308h
0x1800255e2  jz      short loc_1800255ED
0x1800255e4  bts     eax, 16h
0x1800255e8  mov     [rbx+58h], eax
0x1800255eb  jmp     short loc_180025614
0x1800255ed  btr     eax, 16h
0x1800255f1  mov     [rbx+58h], eax
0x1800255f4  test    edi, edi
0x1800255f6  jnz     short loc_180025614
0x1800255f8  bt      eax, 18h
0x1800255fc  jnb     short loc_180025614
0x1800255fe  cmp     [rbx+60h], si
0x180025602  jnz     short loc_18002560D
0x180025604  mov     dword ptr [rbx+54h], 41303h
0x18002560b  jmp     short loc_180025614
0x18002560d  mov     dword ptr [rbx+54h], 41300h
0x180025614  test    al, 4
0x180025616  jz      short loc_18002561F
0x180025618  mov     dword ptr [rbx+54h], 41302h
0x18002561f  xor     eax, eax
0x180025621  mov     rcx, [rbp+var_8]
0x180025625  xor     rcx, rsp; StackCookie
0x180025628  call    __security_check_cookie
0x18002562d  lea     r11, [rsp+60h+var_s0]
0x180025632  mov     rbx, [r11+28h]
0x180025636  mov     rsi, [r11+30h]
0x18002563a  mov     rsp, r11
0x18002563d  pop     r14
0x18002563f  pop     rdi
0x180025640  pop     rbp
0x180025641  retn
```
