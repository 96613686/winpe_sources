# CThirdPartyMonitoring::DetectPresenceAndFillHandleArrays(int)

- ea: `0x18000a570`
- end: `0x18000a735`
- name: `?DetectPresenceAndFillHandleArrays@CThirdPartyMonitoring@@AEAAJH@Z`
- size: `453`
- prototype: `__int64 __fastcall(CThirdPartyMonitoring *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000a740`

## callees

- `0x18000a570`
- `0x18000b2a0`
- `0x18001b420`
- `0x18001ffe4`
- `0x180038a1c`
- `0x18003a8dc`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a6cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a6cd`

## pseudocode

```c
__int64 __fastcall CThirdPartyMonitoring::DetectPresenceAndFillHandleArrays(CThirdPartyMonitoring *this, int a2)
{
  _QWORD *v4; // rcx
  _QWORD *i; // rax
  CDetectoid *Next; // rax
  CDetectoid *v8; // rsi
  int v9; // ebp
  int v10; // eax
  unsigned int v11; // r14d
  unsigned int v12; // ecx
  __int64 j; // rbp
  HANDLE EventW; // rax
  int v15; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp+18h] BYREF

  CThirdPartyMonitoring::ClearHandleArrays(this);
  *((_QWORD *)this + 6) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 7) = *((_QWORD *)this + 3);
  *((_QWORD *)this + 8) = *((_QWORD *)this + 4);
  v4 = (_QWORD *)(*((_QWORD *)this + 135) + 56LL);
  *((_DWORD *)this + 268) = 3;
  for ( i = (_QWORD *)*v4; !i[2]; i = (_QWORD *)*i )
    ;
  if ( i != v4 )
  {
    v16 = i;
    do
    {
      Next = (CDetectoid *)CList<CDetectoid *,CDetectoid *>::GetNext(*((_QWORD *)this + 135), &v16);
      v8 = Next;
      v15 = 0;
      v9 = *((_DWORD *)Next + 14);
      if ( v9 )
        (*(void (__fastcall **)(CDetectoid *))(*(_QWORD *)Next + 32LL))(Next);
      CDetectoid::IsMonitoringEnabled(v8, &v15);
      if ( v15 )
      {
        v10 = (*(__int64 (__fastcall **)(CDetectoid *))(*(_QWORD *)v8 + 24LL))(v8);
        *((_DWORD *)v8 + 14) = v10;
        if ( v10 )
        {
          if ( (*(int (__fastcall **)(CDetectoid *))(*(_QWORD *)v8 + 40LL))(v8) < 0 )
            (*(void (__fastcall **)(CDetectoid *))(*(_QWORD *)v8 + 32LL))(v8);
          v15 = 0;
          CThirdPartyMonitoring::RefreshDetectoidState(this, a2, v8, &v15);
          CThirdPartyMonitoring::UpdateThirdPartyManager(this, v9 != 0, v8);
          v11 = *((_DWORD *)v8 + 10);
          v12 = v11 + *((_DWORD *)this + 268);
          if ( v12 < 0x40 && v12 >= v11 )
          {
            for ( j = 0; (unsigned int)j < v11; ++*((_DWORD *)this + 268) )
            {
              if ( (unsigned int)j >= *((_DWORD *)v8 + 10) || (EventW = (HANDLE)*((_QWORD *)v8 + j + 1)) == 0 )
              {
                EventW = CreateEventW(0, 0, 0, 0);
                *((_QWORD *)this + *((unsigned int *)this + 268) + 70) = EventW;
              }
              j = (unsigned int)(j + 1);
              *((_QWORD *)this + *((unsigned int *)this + 268) + 6) = EventW;
            }
          }
          continue;
        }
        if ( v9 )
LABEL_23:
          CThirdPartyMonitoring::UpdateThirdPartyManager(this, 2, v8);
      }
      else if ( v9 )
      {
        goto LABEL_23;
      }
    }
    while ( v16 );
  }
  return 0;
}

```

## disassembly

```asm
0x18000a570  push    rbx
0x18000a572  push    rdi
0x18000a573  sub     rsp, 28h
0x18000a577  mov     edi, edx
0x18000a579  mov     rbx, rcx
0x18000a57c  call    ?ClearHandleArrays@CThirdPartyMonitoring@@AEAAXXZ; CThirdPartyMonitoring::ClearHandleArrays(void)
0x18000a581  mov     rax, [rbx+8]
0x18000a585  mov     [rbx+30h], rax
0x18000a589  mov     rax, [rbx+18h]
0x18000a58d  mov     [rbx+38h], rax
0x18000a591  mov     rax, [rbx+20h]
0x18000a595  mov     [rbx+40h], rax
0x18000a599  mov     rcx, [rbx+438h]
0x18000a5a0  add     rcx, 38h ; '8'
0x18000a5a4  mov     dword ptr [rbx+430h], 3
0x18000a5ae  mov     rax, [rcx]
0x18000a5b1  cmp     qword ptr [rax+10h], 0
0x18000a5b6  jnz     short loc_18000A5C2
0x18000a5b8  mov     rax, [rax]
0x18000a5bb  cmp     qword ptr [rax+10h], 0
0x18000a5c0  jz      short loc_18000A5B8
0x18000a5c2  cmp     rax, rcx
0x18000a5c5  jnz     short loc_18000A5D0
0x18000a5c7  xor     eax, eax
0x18000a5c9  add     rsp, 28h
0x18000a5cd  pop     rdi
0x18000a5ce  pop     rbx
0x18000a5cf  retn
0x18000a5d0  mov     [rsp+38h+arg_8], rbp
0x18000a5d5  mov     [rsp+38h+arg_18], rsi
0x18000a5da  mov     [rsp+38h+var_18], r14
0x18000a5df  mov     [rsp+38h+arg_10], rax
0x18000a5e4  mov     rcx, [rbx+438h]
0x18000a5eb  lea     rdx, [rsp+38h+arg_10]
0x18000a5f0  call    ?GetNext@?$CList@PEAVCDetectoid@@PEAV1@@@QEAAPEAVCDetectoid@@AEAPEAU_CListElement@@@Z; CList<CDetectoid *,CDetectoid *>::GetNext(_CListElement * &)
0x18000a5f5  mov     rsi, rax
0x18000a5f8  mov     [rsp+38h+arg_0], 0
0x18000a600  mov     ebp, [rax+38h]
0x18000a603  test    ebp, ebp
0x18000a605  jz      short loc_18000A616
0x18000a607  mov     rcx, [rax]
0x18000a60a  mov     rax, [rcx+20h]
0x18000a60e  mov     rcx, rsi
0x18000a611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a616  lea     rdx, [rsp+38h+arg_0]; int *
0x18000a61b  mov     rcx, rsi; this
0x18000a61e  call    ?IsMonitoringEnabled@CDetectoid@@QEAAJAEAH@Z; CDetectoid::IsMonitoringEnabled(int &)
0x18000a623  cmp     [rsp+38h+arg_0], 0
0x18000a628  jz      loc_18000A701
0x18000a62e  mov     rax, [rsi]
0x18000a631  mov     rcx, rsi
0x18000a634  mov     rax, [rax+18h]
0x18000a638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a63d  mov     [rsi+38h], eax
0x18000a640  test    eax, eax
0x18000a642  jz      loc_18000A6FB
0x18000a648  mov     rax, [rsi]
0x18000a64b  mov     rcx, rsi
0x18000a64e  mov     rax, [rax+28h]
0x18000a652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a657  test    eax, eax
0x18000a659  jns     short loc_18000A66A
0x18000a65b  mov     rax, [rsi]
0x18000a65e  mov     rcx, rsi
0x18000a661  mov     rax, [rax+20h]
0x18000a665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a66a  lea     r9, [rsp+38h+arg_0]; int *
0x18000a66f  mov     [rsp+38h+arg_0], 0
0x18000a677  mov     r8, rsi; struct CDetectoid *
0x18000a67a  mov     edx, edi; int
0x18000a67c  mov     rcx, rbx; this
0x18000a67f  call    ?RefreshDetectoidState@CThirdPartyMonitoring@@AEAAJHPEAVCDetectoid@@PEAH@Z; CThirdPartyMonitoring::RefreshDetectoidState(int,CDetectoid *,int *)
0x18000a684  xor     edx, edx
0x18000a686  mov     r8, rsi
0x18000a689  test    ebp, ebp
0x18000a68b  mov     rcx, rbx
0x18000a68e  setnz   dl
0x18000a691  call    ?UpdateThirdPartyManager@CThirdPartyMonitoring@@AEAAJW4THIRDPARTYACTION@@PEAVCDetectoid@@@Z; CThirdPartyMonitoring::UpdateThirdPartyManager(THIRDPARTYACTION,CDetectoid *)
0x18000a696  mov     ecx, [rbx+430h]
0x18000a69c  mov     r14d, [rsi+28h]
0x18000a6a0  add     ecx, r14d
0x18000a6a3  cmp     ecx, 40h ; '@'
0x18000a6a6  jnb     short loc_18000A715
0x18000a6a8  cmp     ecx, r14d
0x18000a6ab  jb      short loc_18000A715
0x18000a6ad  xor     ebp, ebp
0x18000a6af  test    r14d, r14d
0x18000a6b2  jz      short loc_18000A715
0x18000a6b4  cmp     ebp, [rsi+28h]
0x18000a6b7  jnb     short loc_18000A6C3
0x18000a6b9  mov     rax, [rsi+rbp*8+8]
0x18000a6be  test    rax, rax
0x18000a6c1  jnz     short loc_18000A6E1
0x18000a6c3  xor     r9d, r9d; lpName
0x18000a6c6  xor     r8d, r8d; bInitialState
0x18000a6c9  xor     edx, edx; bManualReset
0x18000a6cb  xor     ecx, ecx; lpEventAttributes
0x18000a6cd  call    cs:__imp_CreateEventW
0x18000a6d3  mov     ecx, [rbx+430h]
0x18000a6d9  mov     [rbx+rcx*8+230h], rax
0x18000a6e1  mov     ecx, [rbx+430h]
0x18000a6e7  inc     ebp
0x18000a6e9  mov     [rbx+rcx*8+30h], rax
0x18000a6ee  inc     dword ptr [rbx+430h]
0x18000a6f4  cmp     ebp, r14d
0x18000a6f7  jb      short loc_18000A6B4
0x18000a6f9  jmp     short loc_18000A715
0x18000a6fb  test    ebp, ebp
0x18000a6fd  jz      short loc_18000A715
0x18000a6ff  jmp     short loc_18000A705
0x18000a701  test    ebp, ebp
0x18000a703  jz      short loc_18000A715
0x18000a705  mov     r8, rsi
0x18000a708  mov     edx, 2
0x18000a70d  mov     rcx, rbx
0x18000a710  call    ?UpdateThirdPartyManager@CThirdPartyMonitoring@@AEAAJW4THIRDPARTYACTION@@PEAVCDetectoid@@@Z; CThirdPartyMonitoring::UpdateThirdPartyManager(THIRDPARTYACTION,CDetectoid *)
0x18000a715  cmp     [rsp+38h+arg_10], 0
0x18000a71b  jnz     loc_18000A5E4
0x18000a721  mov     r14, [rsp+38h+var_18]
0x18000a726  mov     rsi, [rsp+38h+arg_18]
0x18000a72b  mov     rbp, [rsp+38h+arg_8]
0x18000a730  jmp     loc_18000A5C7
```
