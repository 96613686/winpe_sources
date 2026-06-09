# TfsDeleteEntry

- ea: `0x18002ae00`
- end: `0x18002afa8`
- name: `TfsDeleteEntry`
- size: `424`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001bd74`
- `0x18001dfc0`
- `0x18001f190`

## callees

- `0x18000b7dc`
- `0x18000b93c`
- `0x18000bc5c`
- `0x180014f50`
- `0x18002ae00`
- `0x18002afb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae34`

## pseudocode

```c
__int64 __fastcall TfsDeleteEntry(__int64 a1, __int64 a2)
{
  HLOCAL v2; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  unsigned int Entry; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v2 = DavTfsStore;
  v9 = 0;
  if ( !DavTfsStore )
    return 6;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)DavTfsStore + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DavTfsStore + 56));
  Entry = TfsFindEntry(v2, a2, &v9);
  v7 = Entry;
  if ( Entry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, Entry);
    LeaveCriticalSection(v5);
    return v7;
  }
  else
  {
    v8 = v9;
    if ( v9 && *(_DWORD *)(v9 + 24) == 1 )
    {
      if ( *(_DWORD *)(v9 + 20) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
            v9,
            *(_DWORD *)(v9 + 20));
        --*(_DWORD *)(v8 + 20);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v9);
      }
      *(_DWORD *)(v8 + 24) = 2;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
          v8,
          *(_DWORD *)(v8 + 20));
      LeaveCriticalSection(v5);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, a2);
      LeaveCriticalSection(v5);
      return 2;
    }
  }
}

```

## disassembly

```asm
0x18002ae00  mov     [rsp+arg_0], rcx
0x18002ae05  push    rbx
0x18002ae06  push    rbp
0x18002ae07  push    rsi
0x18002ae08  push    rdi
0x18002ae09  sub     rsp, 38h
0x18002ae0d  mov     rbx, cs:DavTfsStore
0x18002ae14  mov     rbp, rdx
0x18002ae17  mov     [rsp+58h+arg_0], 0
0x18002ae20  test    rbx, rbx
0x18002ae23  jnz     short loc_18002AE2D
0x18002ae25  lea     eax, [rbx+6]
0x18002ae28  jmp     loc_18002AF9F
0x18002ae2d  lea     rsi, [rbx+38h]
0x18002ae31  mov     rcx, rsi; lpCriticalSection
0x18002ae34  call    cs:__imp_EnterCriticalSection
0x18002ae3a  lea     r8, [rsp+58h+arg_0]
0x18002ae3f  mov     rdx, rbp
0x18002ae42  mov     rcx, rbx
0x18002ae45  call    TfsFindEntry
0x18002ae4a  mov     ebx, eax
0x18002ae4c  test    eax, eax
0x18002ae4e  jz      short loc_18002AE91
0x18002ae50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae57  lea     rdi, WPP_GLOBAL_Control
0x18002ae5e  cmp     rcx, rdi
0x18002ae61  jz      short loc_18002AE81
0x18002ae63  test    byte ptr [rcx+1Ch], 1
0x18002ae67  jz      short loc_18002AE81
0x18002ae69  mov     rcx, [rcx+10h]
0x18002ae6d  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002ae74  mov     edx, 40h ; '@'
0x18002ae79  mov     r9d, eax
0x18002ae7c  call    WPP_SF_d
0x18002ae81  mov     rcx, rsi; lpCriticalSection
0x18002ae84  call    cs:__imp_LeaveCriticalSection
0x18002ae8a  mov     eax, ebx
0x18002ae8c  jmp     loc_18002AF9F
0x18002ae91  mov     rbx, [rsp+58h+arg_0]
0x18002ae96  test    rbx, rbx
0x18002ae99  jz      loc_18002AF60
0x18002ae9f  cmp     dword ptr [rbx+18h], 1
0x18002aea3  jnz     loc_18002AF60
0x18002aea9  mov     eax, [rbx+14h]
0x18002aeac  test    eax, eax
0x18002aeae  jz      short loc_18002AEEA
0x18002aeb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aeb7  lea     rdi, WPP_GLOBAL_Control
0x18002aebe  cmp     rcx, rdi
0x18002aec1  jz      short loc_18002AEE5
0x18002aec3  test    byte ptr [rcx+1Ch], 2
0x18002aec7  jz      short loc_18002AEE5
0x18002aec9  mov     rcx, [rcx+10h]
0x18002aecd  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002aed4  mov     edx, 42h ; 'B'
0x18002aed9  mov     [rsp+58h+var_38], eax
0x18002aedd  mov     r9, rbx
0x18002aee0  call    WPP_SF_qd
0x18002aee5  dec     dword ptr [rbx+14h]
0x18002aee8  jmp     short loc_18002AF1B
0x18002aeea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aef1  lea     rdi, WPP_GLOBAL_Control
0x18002aef8  cmp     rcx, rdi
0x18002aefb  jz      short loc_18002AF1B
0x18002aefd  test    byte ptr [rcx+1Ch], 1
0x18002af01  jz      short loc_18002AF1B
0x18002af03  mov     rcx, [rcx+10h]
0x18002af07  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002af0e  mov     edx, 43h ; 'C'
0x18002af13  mov     r9, rbx
0x18002af16  call    WPP_SF_q
0x18002af1b  mov     dword ptr [rbx+18h], 2
0x18002af22  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af29  cmp     rcx, rdi
0x18002af2c  jz      short loc_18002AF53
0x18002af2e  test    byte ptr [rcx+1Ch], 2
0x18002af32  jz      short loc_18002AF53
0x18002af34  mov     eax, [rbx+14h]
0x18002af37  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002af3e  mov     rcx, [rcx+10h]
0x18002af42  mov     edx, 44h ; 'D'
0x18002af47  mov     r9, rbx
0x18002af4a  mov     [rsp+58h+var_38], eax
0x18002af4e  call    WPP_SF_qd
0x18002af53  mov     rcx, rsi; lpCriticalSection
0x18002af56  call    cs:__imp_LeaveCriticalSection
0x18002af5c  xor     eax, eax
0x18002af5e  jmp     short loc_18002AF9F
0x18002af60  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af67  lea     rdi, WPP_GLOBAL_Control
0x18002af6e  cmp     rcx, rdi
0x18002af71  jz      short loc_18002AF91
0x18002af73  test    byte ptr [rcx+1Ch], 1
0x18002af77  jz      short loc_18002AF91
0x18002af79  mov     rcx, [rcx+10h]
0x18002af7d  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002af84  mov     edx, 41h ; 'A'
0x18002af89  mov     r9, rbp
0x18002af8c  call    WPP_SF_S
0x18002af91  mov     rcx, rsi; lpCriticalSection
0x18002af94  call    cs:__imp_LeaveCriticalSection
0x18002af9a  mov     eax, 2
0x18002af9f  add     rsp, 38h
0x18002afa3  pop     rdi
0x18002afa4  pop     rsi
0x18002afa5  pop     rbp
0x18002afa6  pop     rbx
0x18002afa7  retn
```
