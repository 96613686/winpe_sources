# GSM::_ProcessServiceControlCodes(GSM::SERVICEENTRY *)

- ea: `0x1800077e0`
- end: `0x180007ac6`
- name: `?_ProcessServiceControlCodes@GSM@@YAJPEAUSERVICEENTRY@1@@Z`
- size: `742`
- prototype: `__int64 __fastcall(GSM *__hidden this, struct GSM::SERVICEENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007760`

## callees

- `0x1800077e0`
- `0x180007ad0`
- `0x180018a74`
- `0x180022130`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000786a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000786a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078f1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007817`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007817`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007843`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007843`

## pseudocode

```c
__int64 __fastcall GSM::_ProcessServiceControlCodes(GSM *this, struct GSM::SERVICEENTRY *a2)
{
  int v3; // ebp
  __int64 v4; // rdi
  __int64 v5; // rax
  struct GSM::SERVICEENTRY *v6; // rdx
  int v7; // ecx
  int v8; // r8d
  int v9; // eax
  int v10; // r14d
  int v11; // esi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // esi
  _BYTE v21[16]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-40h] BYREF

  v3 = 0;
  while ( 1 )
  {
    EnterCriticalSection(&stru_18003E3F0);
    v4 = *((_QWORD *)this + 7);
    v5 = *(_QWORD *)(v4 + 16);
    if ( !v5 )
      *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 7) = v5;
    *(_QWORD *)(v4 + 16) = 0;
    if ( !*((_QWORD *)this + 7) )
    {
      v3 = 1;
      ResetEvent(*((HANDLE *)this + 35));
    }
    LeaveCriticalSection(&stru_18003E3F0);
    v9 = *(_DWORD *)(v4 + 24);
    switch ( v9 )
    {
      case 11:
        if ( (*(_BYTE *)this & 1) == 0 )
          goto LABEL_8;
LABEL_14:
        if ( !*((_DWORD *)this + 18) )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 37) + 56LL))(
                  *((_QWORD *)this + 37),
                  v4);
          goto LABEL_16;
        }
LABEL_48:
        v10 = 0;
        goto LABEL_16;
      case 13:
        v10 = (*((_DWORD *)this + 1) & 0x40) == 0;
        goto LABEL_12;
      case 1:
        if ( *((_DWORD *)this + 3) != 1 )
        {
          *((_DWORD *)this + 3) = 3;
          goto LABEL_47;
        }
        break;
      case 2:
        if ( *((_DWORD *)this + 3) != 1 && *((_DWORD *)this + 3) != 7 )
        {
          *((_DWORD *)this + 3) = 6;
          goto LABEL_47;
        }
        break;
      default:
        v7 = v9 - 3;
        if ( v9 != 3 )
        {
          if ( v9 == 14 )
            goto LABEL_23;
          break;
        }
        if ( *((_DWORD *)this + 3) != 1 && *((_DWORD *)this + 3) != 4 )
        {
          *((_DWORD *)this + 3) = 5;
LABEL_47:
          v10 = 0;
          goto LABEL_11;
        }
        break;
    }
    v10 = 1;
LABEL_11:
    GSM::_SetServiceStatus(this, v6);
    v9 = *(_DWORD *)(v4 + 24);
LABEL_12:
    if ( v10 )
      goto LABEL_16;
    if ( v9 == 11 )
      goto LABEL_14;
LABEL_23:
    v13 = v9 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 10;
          if ( v16 )
          {
            if ( v16 != 1 )
            {
LABEL_8:
              v10 = 1;
              goto LABEL_16;
            }
            if ( !*((_DWORD *)this + 18) )
            {
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 37) + 80LL))(
                      *((_QWORD *)this + 37),
                      v4);
              goto LABEL_16;
            }
          }
          else if ( !*((_DWORD *)this + 18) )
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 37) + 64LL))(
                    *((_QWORD *)this + 37),
                    v4);
            goto LABEL_16;
          }
          goto LABEL_48;
        }
      }
    }
    if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v7,
        (unsigned int)ShellTraceId_HDSrv_Service_Stop_Start,
        v8,
        1,
        (__int64)v21);
    do
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 37) + 32LL))(
              *((_QWORD *)this + 37),
              *(unsigned int *)(v4 + 24),
              (char *)this + 32);
      v20 = v17;
      v10 = v17;
      if ( v17 < 0 )
        break;
      v10 = GSM::_HandlePostState(this, (struct GSM::SERVICEENTRY *)*(unsigned int *)(v4 + 24), v17 == 1);
      if ( v10 < 0 )
        break;
    }
    while ( v20 == 1 );
    if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v18,
        (unsigned int)ShellTraceId_HDSrv_Service_Stop_Stop,
        v19,
        1,
        (__int64)v22);
LABEL_16:
    v11 = 0;
    if ( *(_DWORD *)(v4 + 24) != 11 )
      v11 = v10;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    if ( v3 )
      break;
    if ( v11 < 0 )
      return (unsigned int)v11;
  }
  SetEvent(*((HANDLE *)this + 36));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800077e0  mov     [rsp+arg_8], rbx
0x1800077e5  mov     [rsp+arg_10], rbp
0x1800077ea  push    rsi
0x1800077eb  push    rdi
0x1800077ec  push    r12
0x1800077ee  push    r14
0x1800077f0  push    r15
0x1800077f2  sub     rsp, 60h
0x1800077f6  mov     rax, cs:__security_cookie
0x1800077fd  xor     rax, rsp
0x180007800  mov     [rsp+88h+var_30], rax
0x180007805  xor     r12d, r12d
0x180007808  mov     rbx, rcx
0x18000780b  mov     ebp, r12d
0x18000780e  xchg    ax, ax
0x180007810  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180007817  call    cs:__imp_EnterCriticalSection
0x18000781d  mov     rdi, [rbx+38h]
0x180007821  mov     rax, [rdi+10h]
0x180007825  test    rax, rax
0x180007828  jnz     short loc_18000782E
0x18000782a  mov     [rbx+40h], r12
0x18000782e  mov     [rbx+38h], rax
0x180007832  mov     [rdi+10h], r12
0x180007836  cmp     [rbx+38h], r12
0x18000783a  jz      short loc_18000785E
0x18000783c  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180007843  call    cs:__imp_LeaveCriticalSection
0x180007849  mov     eax, [rdi+18h]
0x18000784c  cmp     eax, 0Bh
0x18000784f  jnz     short loc_180007872
0x180007851  test    byte ptr [rbx], 1
0x180007854  jnz     short loc_1800078A5
0x180007856  mov     r14d, 1
0x18000785c  jmp     short loc_1800078C8
0x18000785e  mov     rcx, [rbx+118h]; hEvent
0x180007865  mov     ebp, 1
0x18000786a  call    cs:__imp_ResetEvent
0x180007870  jmp     short loc_18000783C
0x180007872  cmp     eax, 0Dh
0x180007875  jnz     loc_1800079BA
0x18000787b  mov     r14d, [rbx+4]
0x18000787f  shr     r14d, 6
0x180007883  not     r14d
0x180007886  and     r14d, 1
0x18000788a  jmp     short loc_180007897
0x18000788c  mov     rcx, rbx; this
0x18000788f  call    ?_SetServiceStatus@GSM@@YAXPEAUSERVICEENTRY@1@@Z; GSM::_SetServiceStatus(GSM::SERVICEENTRY *)
0x180007894  mov     eax, [rdi+18h]
0x180007897  test    r14d, r14d
0x18000789a  jnz     short loc_1800078C8
0x18000789c  cmp     eax, 0Bh
0x18000789f  jnz     loc_180007934
0x1800078a5  cmp     [rbx+48h], r12d
0x1800078a9  jnz     loc_180007A27
0x1800078af  mov     rcx, [rbx+128h]
0x1800078b6  mov     rdx, rdi
0x1800078b9  mov     rax, [rcx]
0x1800078bc  mov     rax, [rax+38h]
0x1800078c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c5  mov     r14d, eax
0x1800078c8  cmp     dword ptr [rdi+18h], 0Bh
0x1800078cc  mov     esi, r12d
0x1800078cf  mov     eax, 0FFFFFFFFh
0x1800078d4  cmovnz  esi, r14d
0x1800078d8  lock xadd [rdi+8], eax
0x1800078dd  cmp     eax, 1
0x1800078e0  jz      short loc_18000791F
0x1800078e2  test    ebp, ebp
0x1800078e4  jz      loc_1800079AD
0x1800078ea  mov     rcx, [rbx+120h]; hEvent
0x1800078f1  call    cs:__imp_SetEvent
0x1800078f7  mov     eax, esi
0x1800078f9  mov     rcx, [rsp+88h+var_30]
0x1800078fe  xor     rcx, rsp; StackCookie
0x180007901  call    __security_check_cookie
0x180007906  lea     r11, [rsp+88h+var_28]
0x18000790b  mov     rbx, [r11+38h]
0x18000790f  mov     rbp, [r11+40h]
0x180007913  mov     rsp, r11
0x180007916  pop     r15
0x180007918  pop     r14
0x18000791a  pop     r12
0x18000791c  pop     rdi
0x18000791d  pop     rsi
0x18000791e  retn
0x18000791f  mov     rcx, [rdi]
0x180007922  mov     edx, 1
0x180007927  mov     rax, [rcx]
0x18000792a  mov     rcx, rdi
0x18000792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007932  jmp     short loc_1800078E2
0x180007934  sub     eax, 1
0x180007937  jz      loc_180007A2F
0x18000793d  sub     eax, 1
0x180007940  jz      loc_180007A2F
0x180007946  sub     eax, 1
0x180007949  jz      loc_180007A2F
0x18000794f  sub     eax, 0Ah
0x180007952  jnz     short loc_18000797C
0x180007954  cmp     [rbx+48h], r12d
0x180007958  jnz     loc_180007A27
0x18000795e  mov     rcx, [rbx+128h]
0x180007965  mov     rdx, rdi
0x180007968  mov     rax, [rcx]
0x18000796b  mov     rax, [rax+40h]
0x18000796f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007974  mov     r14d, eax
0x180007977  jmp     loc_1800078C8
0x18000797c  cmp     eax, 1
0x18000797f  jnz     loc_180007856
0x180007985  cmp     [rbx+48h], r12d
0x180007989  jnz     loc_180007A27
0x18000798f  mov     rcx, [rbx+128h]
0x180007996  mov     rdx, rdi
0x180007999  mov     rax, [rcx]
0x18000799c  mov     rax, [rax+50h]
0x1800079a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a5  mov     r14d, eax
0x1800079a8  jmp     loc_1800078C8
0x1800079ad  test    esi, esi
0x1800079af  jns     loc_180007810
0x1800079b5  jmp     loc_1800078F7
0x1800079ba  mov     ecx, eax
0x1800079bc  sub     ecx, 1
0x1800079bf  jz      short loc_180007A10
0x1800079c1  sub     ecx, 1
0x1800079c4  jz      short loc_1800079F5
0x1800079c6  sub     ecx, 1
0x1800079c9  jz      short loc_1800079DF
0x1800079cb  cmp     ecx, 0Bh
0x1800079ce  jz      loc_180007934
0x1800079d4  mov     r14d, 1
0x1800079da  jmp     loc_18000788C
0x1800079df  mov     ecx, [rbx+0Ch]
0x1800079e2  sub     ecx, 1
0x1800079e5  jz      short loc_1800079D4
0x1800079e7  cmp     ecx, 3
0x1800079ea  jz      short loc_1800079D4
0x1800079ec  mov     dword ptr [rbx+0Ch], 5
0x1800079f3  jmp     short loc_180007A1F
0x1800079f5  mov     ecx, [rbx+0Ch]
0x1800079f8  sub     ecx, 1
0x1800079fb  jz      short loc_1800079D4
0x1800079fd  sub     ecx, 3
0x180007a00  jz      short loc_180007A07
0x180007a02  cmp     ecx, 3
0x180007a05  jz      short loc_1800079D4
0x180007a07  mov     dword ptr [rbx+0Ch], 6
0x180007a0e  jmp     short loc_180007A1F
0x180007a10  mov     ecx, [rbx+0Ch]
0x180007a13  sub     ecx, 1
0x180007a16  jz      short loc_1800079D4
0x180007a18  mov     dword ptr [rbx+0Ch], 3
0x180007a1f  mov     r14d, r12d
0x180007a22  jmp     loc_18000788C
0x180007a27  mov     r14d, r12d
0x180007a2a  jmp     loc_1800078C8
0x180007a2f  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x180007a36  jz      short loc_180007A54
0x180007a38  lea     rax, [rsp+88h+var_50]
0x180007a3d  mov     r9d, 1
0x180007a43  lea     rdx, ShellTraceId_HDSrv_Service_Stop_Start
0x180007a4a  mov     [rsp+88h+var_68], rax
0x180007a4f  call    McGenEventWrite_EtwEventWriteTransfer
0x180007a54  mov     rcx, [rbx+128h]
0x180007a5b  lea     r8, [rbx+20h]
0x180007a5f  mov     edx, [rdi+18h]
0x180007a62  mov     rax, [rcx]
0x180007a65  mov     rax, [rax+20h]
0x180007a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6e  mov     esi, eax
0x180007a70  mov     r14d, eax
0x180007a73  test    eax, eax
0x180007a75  js      short loc_180007A98
0x180007a77  mov     edx, [rdi+18h]; struct GSM::SERVICEENTRY *
0x180007a7a  cmp     eax, 1
0x180007a7d  mov     r8d, r12d
0x180007a80  mov     rcx, rbx; this
0x180007a83  setz    r8b; unsigned int
0x180007a87  call    ?_HandlePostState@GSM@@YAJPEAUSERVICEENTRY@1@KH@Z; GSM::_HandlePostState(GSM::SERVICEENTRY *,ulong,int)
0x180007a8c  mov     r14d, eax
0x180007a8f  test    eax, eax
0x180007a91  js      short loc_180007A98
0x180007a93  cmp     esi, 1
0x180007a96  jz      short loc_180007A54
0x180007a98  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x180007a9f  jz      loc_1800078C8
0x180007aa5  lea     rax, [rsp+88h+var_40]
0x180007aaa  mov     r9d, 1
0x180007ab0  lea     rdx, ShellTraceId_HDSrv_Service_Stop_Stop
0x180007ab7  mov     [rsp+88h+var_68], rax
0x180007abc  call    McGenEventWrite_EtwEventWriteTransfer
0x180007ac1  jmp     loc_1800078C8
```
