# __DllMainCRTStartup

- ea: `0x180001604`
- end: `0x180001810`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015c0`

## callees

- `0x1800011d0`
- `0x180001390`
- `0x180001604`
- `0x180001f29`
- `0x18002d8b0`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_18003FA80 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003FA84 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18003FA84 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001604  mov     [rsp+lpvReserved], r8
0x180001609  mov     [rsp+arg_8], edx
0x18000160d  mov     [rsp+arg_0], rcx
0x180001612  push    rbx
0x180001613  push    rsi
0x180001614  push    rdi
0x180001615  sub     rsp, 0F0h
0x18000161c  mov     edi, edx
0x18000161e  mov     rsi, rcx
0x180001621  mov     ebx, 1
0x180001626  cmp     edx, ebx
0x180001628  ja      short loc_180001630
0x18000162a  mov     cs:__native_dllmain_reason, edx
0x180001630  test    edx, edx
0x180001632  jnz     short loc_180001647
0x180001634  cmp     cs:dword_18003FA80, edx
0x18000163a  jnz     short loc_180001647
0x18000163c  xor     ebx, ebx
0x18000163e  mov     [rsp+108h+var_E8], ebx
0x180001642  jmp     loc_1800017F4
0x180001647  lea     eax, [rdx-1]
0x18000164a  cmp     eax, 1
0x18000164d  ja      loc_1800016D4
0x180001653  mov     rax, cs:_pRawDllMain
0x18000165a  test    rax, rax
0x18000165d  jz      short loc_180001695
0x18000165f  cmp     edx, 1
0x180001662  jnz     short loc_18000166A
0x180001664  mov     cs:dword_18003FA84, edx
0x18000166a  mov     r8, [rsp+108h+lpvReserved]
0x180001672  call    cs:__guard_dispatch_icall_fptr
0x180001678  mov     ebx, eax
0x18000167a  mov     [rsp+108h+var_E8], eax
0x18000167e  jmp     short loc_180001695
0x180001680  xor     ebx, ebx
0x180001682  mov     [rsp+108h+var_E8], ebx
0x180001686  mov     edi, [rsp+108h+arg_8]
0x18000168d  mov     rsi, [rsp+108h+arg_0]
0x180001695  test    ebx, ebx
0x180001697  jz      loc_1800017F4
0x18000169d  mov     r8, [rsp+108h+lpvReserved]
0x1800016a5  mov     edx, edi
0x1800016a7  mov     rcx, rsi
0x1800016aa  call    _CRT_INIT
0x1800016af  mov     ebx, eax
0x1800016b1  mov     [rsp+108h+var_E8], eax
0x1800016b5  jmp     short loc_1800016CC
0x1800016b7  xor     ebx, ebx
0x1800016b9  mov     [rsp+108h+var_E8], ebx
0x1800016bd  mov     edi, [rsp+108h+arg_8]
0x1800016c4  mov     rsi, [rsp+108h+arg_0]
0x1800016cc  test    ebx, ebx
0x1800016ce  jz      loc_1800017F4
0x1800016d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016dc  mov     edx, edi; fdwReason
0x1800016de  mov     rcx, rsi; hinstDLL
0x1800016e1  call    DllMain
0x1800016e6  mov     ebx, eax
0x1800016e8  mov     [rsp+108h+var_E8], eax
0x1800016ec  jmp     short loc_180001703
0x1800016ee  xor     ebx, ebx
0x1800016f0  mov     [rsp+108h+var_E8], ebx
0x1800016f4  mov     edi, [rsp+108h+arg_8]
0x1800016fb  mov     rsi, [rsp+108h+arg_0]
0x180001703  cmp     edi, 1
0x180001706  jnz     short loc_18000177F
0x180001708  test    ebx, ebx
0x18000170a  jnz     short loc_18000177F
0x18000170c  xor     r8d, r8d; lpvReserved
0x18000170f  xor     edx, edx; fdwReason
0x180001711  mov     rcx, rsi; hinstDLL
0x180001714  call    DllMain
0x180001719  jmp     short loc_18000172E
0x18000171b  mov     edi, [rsp+108h+arg_8]
0x180001722  mov     rsi, [rsp+108h+arg_0]
0x18000172a  mov     ebx, [rsp+108h+var_E8]
0x18000172e  xor     r8d, r8d
0x180001731  xor     edx, edx
0x180001733  mov     rcx, rsi
0x180001736  call    _CRT_INIT
0x18000173b  jmp     short loc_180001750
0x18000173d  mov     edi, [rsp+108h+arg_8]
0x180001744  mov     rsi, [rsp+108h+arg_0]
0x18000174c  mov     ebx, [rsp+108h+var_E8]
0x180001750  mov     rax, cs:_pRawDllMain
0x180001757  test    rax, rax
0x18000175a  jz      short loc_18000177F
0x18000175c  xor     r8d, r8d
0x18000175f  xor     edx, edx
0x180001761  mov     rcx, rsi
0x180001764  call    cs:__guard_dispatch_icall_fptr
0x18000176a  jmp     short loc_18000177F
0x18000176c  mov     edi, [rsp+108h+arg_8]
0x180001773  mov     rsi, [rsp+108h+arg_0]
0x18000177b  mov     ebx, [rsp+108h+var_E8]
0x18000177f  test    edi, edi
0x180001781  jz      short loc_180001788
0x180001783  cmp     edi, 3
0x180001786  jnz     short loc_1800017F4
0x180001788  mov     r8, [rsp+108h+lpvReserved]
0x180001790  mov     edx, edi
0x180001792  mov     rcx, rsi
0x180001795  call    _CRT_INIT
0x18000179a  mov     ebx, eax
0x18000179c  mov     [rsp+108h+var_E8], eax
0x1800017a0  jmp     short loc_1800017B7
0x1800017a2  xor     ebx, ebx
0x1800017a4  mov     [rsp+108h+var_E8], ebx
0x1800017a8  mov     edi, [rsp+108h+arg_8]
0x1800017af  mov     rsi, [rsp+108h+arg_0]
0x1800017b7  mov     rax, cs:_pRawDllMain
0x1800017be  test    rax, rax
0x1800017c1  jz      short loc_1800017F4
0x1800017c3  cmp     cs:dword_18003FA84, 0
0x1800017ca  jz      short loc_1800017F4
0x1800017cc  mov     r8, [rsp+108h+lpvReserved]
0x1800017d4  mov     edx, edi
0x1800017d6  mov     rcx, rsi
0x1800017d9  call    cs:__guard_dispatch_icall_fptr
0x1800017df  mov     ebx, eax
0x1800017e1  mov     [rsp+108h+var_E8], eax
0x1800017e5  jmp     short loc_1800017F4
0x1800017e7  xor     ebx, ebx
0x1800017e9  mov     [rsp+108h+var_E8], ebx
0x1800017ed  mov     edi, [rsp+108h+arg_8]
0x1800017f4  cmp     edi, 1
0x1800017f7  ja      short loc_180001803
0x1800017f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001803  mov     eax, ebx
0x180001805  add     rsp, 0F0h
0x18000180c  pop     rdi
0x18000180d  pop     rsi
0x18000180e  pop     rbx
0x18000180f  retn
0x18002d953  push    rbp
0x18002d955  sub     rsp, 20h
0x18002d959  mov     rbp, rdx
0x18002d95c  mov     rax, [rcx]
0x18002d95f  mov     edx, [rax]
0x18002d961  mov     [rbp+0A8h], rcx
0x18002d968  mov     [rbp+28h], edx
0x18002d96b  mov     eax, [rbp+28h]
0x18002d96e  cmp     eax, 0E06D7363h
0x18002d973  jnz     short loc_18002D989
0x18002d975  mov     rdx, [rbp+0A8h]
0x18002d97c  mov     ecx, [rbp+28h]
0x18002d97f  call    _XcptFilter_0
0x18002d984  mov     [rbp+30h], eax
0x18002d987  jmp     short loc_18002D990
0x18002d989  mov     dword ptr [rbp+30h], 0
0x18002d990  mov     eax, [rbp+30h]
0x18002d993  add     rsp, 20h
0x18002d997  pop     rbp
0x18002d998  retn
0x18002d99a  push    rbp
0x18002d99c  sub     rsp, 20h
0x18002d9a0  mov     rbp, rdx
0x18002d9a3  mov     rax, [rcx]
0x18002d9a6  mov     edx, [rax]
0x18002d9a8  mov     [rbp+0B0h], rcx
0x18002d9af  mov     [rbp+38h], edx
0x18002d9b2  mov     eax, [rbp+38h]
0x18002d9b5  cmp     eax, 0E06D7363h
0x18002d9ba  jnz     short loc_18002D9D0
0x18002d9bc  mov     rdx, [rbp+0B0h]
0x18002d9c3  mov     ecx, [rbp+38h]
0x18002d9c6  call    _XcptFilter_0
0x18002d9cb  mov     [rbp+40h], eax
0x18002d9ce  jmp     short loc_18002D9D7
0x18002d9d0  mov     dword ptr [rbp+40h], 0
0x18002d9d7  mov     eax, [rbp+40h]
0x18002d9da  add     rsp, 20h
0x18002d9de  pop     rbp
0x18002d9df  retn
0x18002d9e1  push    rbp
0x18002d9e3  sub     rsp, 20h
0x18002d9e7  mov     rbp, rdx
0x18002d9ea  mov     rax, [rcx]
0x18002d9ed  mov     edx, [rax]
0x18002d9ef  mov     [rbp+0B8h], rcx
0x18002d9f6  mov     [rbp+48h], edx
0x18002d9f9  mov     eax, [rbp+48h]
0x18002d9fc  cmp     eax, 0E06D7363h
0x18002da01  jnz     short loc_18002DA17
0x18002da03  mov     rdx, [rbp+0B8h]
0x18002da0a  mov     ecx, [rbp+48h]
0x18002da0d  call    _XcptFilter_0
0x18002da12  mov     [rbp+50h], eax
0x18002da15  jmp     short loc_18002DA1E
0x18002da17  mov     dword ptr [rbp+50h], 0
0x18002da1e  mov     eax, [rbp+50h]
0x18002da21  add     rsp, 20h
0x18002da25  pop     rbp
0x18002da26  retn
0x18002da28  push    rbp
0x18002da2a  sub     rsp, 20h
0x18002da2e  mov     rbp, rdx
0x18002da31  mov     rax, [rcx]
0x18002da34  mov     edx, [rax]
0x18002da36  mov     [rbp+0C0h], rcx
0x18002da3d  mov     [rbp+58h], edx
0x18002da40  mov     eax, [rbp+58h]
0x18002da43  cmp     eax, 0E06D7363h
0x18002da48  jnz     short loc_18002DA5E
0x18002da4a  mov     rdx, [rbp+0C0h]
0x18002da51  mov     ecx, [rbp+58h]
0x18002da54  call    _XcptFilter_0
0x18002da59  mov     [rbp+60h], eax
0x18002da5c  jmp     short loc_18002DA65
0x18002da5e  mov     dword ptr [rbp+60h], 0
0x18002da65  mov     eax, [rbp+60h]
0x18002da68  add     rsp, 20h
0x18002da6c  pop     rbp
0x18002da6d  retn
0x18002da6f  push    rbp
0x18002da71  sub     rsp, 20h
0x18002da75  mov     rbp, rdx
0x18002da78  mov     rax, [rcx]
0x18002da7b  mov     edx, [rax]
0x18002da7d  mov     [rbp+0C8h], rcx
0x18002da84  mov     [rbp+68h], edx
0x18002da87  mov     eax, [rbp+68h]
0x18002da8a  cmp     eax, 0E06D7363h
0x18002da8f  jnz     short loc_18002DAA5
0x18002da91  mov     rdx, [rbp+0C8h]
0x18002da98  mov     ecx, [rbp+68h]
0x18002da9b  call    _XcptFilter_0
0x18002daa0  mov     [rbp+70h], eax
0x18002daa3  jmp     short loc_18002DAAC
0x18002daa5  mov     dword ptr [rbp+70h], 0
0x18002daac  mov     eax, [rbp+70h]
0x18002daaf  add     rsp, 20h
0x18002dab3  pop     rbp
0x18002dab4  retn
0x18002dab6  push    rbp
0x18002dab8  sub     rsp, 20h
0x18002dabc  mov     rbp, rdx
0x18002dabf  mov     rax, [rcx]
0x18002dac2  mov     edx, [rax]
0x18002dac4  mov     [rbp+0D0h], rcx
0x18002dacb  mov     [rbp+78h], edx
0x18002dace  mov     eax, [rbp+78h]
0x18002dad1  cmp     eax, 0E06D7363h
0x18002dad6  jnz     short loc_18002DAEF
0x18002dad8  mov     rdx, [rbp+0D0h]
0x18002dadf  mov     ecx, [rbp+78h]
0x18002dae2  call    _XcptFilter_0
0x18002dae7  mov     [rbp+80h], eax
0x18002daed  jmp     short loc_18002DAF9
0x18002daef  mov     dword ptr [rbp+80h], 0
0x18002daf9  mov     eax, [rbp+80h]
0x18002daff  add     rsp, 20h
0x18002db03  pop     rbp
0x18002db04  retn
0x18002db06  push    rbp
0x18002db08  sub     rsp, 20h
0x18002db0c  mov     rbp, rdx
0x18002db0f  mov     rax, [rcx]
0x18002db12  mov     edx, [rax]
0x18002db14  mov     [rbp+0D8h], rcx
0x18002db1b  mov     [rbp+88h], edx
0x18002db21  mov     eax, [rbp+88h]
0x18002db27  cmp     eax, 0E06D7363h
0x18002db2c  jnz     short loc_18002DB48
0x18002db2e  mov     rdx, [rbp+0D8h]
0x18002db35  mov     ecx, [rbp+88h]
0x18002db3b  call    _XcptFilter_0
0x18002db40  mov     [rbp+90h], eax
0x18002db46  jmp     short loc_18002DB52
0x18002db48  mov     dword ptr [rbp+90h], 0
0x18002db52  mov     eax, [rbp+90h]
0x18002db58  add     rsp, 20h
0x18002db5c  pop     rbp
0x18002db5d  retn
0x18002db5f  push    rbp
0x18002db61  sub     rsp, 20h
0x18002db65  mov     rbp, rdx
0x18002db68  mov     rax, [rcx]
0x18002db6b  mov     edx, [rax]
0x18002db6d  mov     [rbp+0E0h], rcx
0x18002db74  mov     [rbp+98h], edx
0x18002db7a  mov     eax, [rbp+98h]
0x18002db80  cmp     eax, 0E06D7363h
0x18002db85  jnz     short loc_18002DBA1
0x18002db87  mov     rdx, [rbp+0E0h]
0x18002db8e  mov     ecx, [rbp+98h]
0x18002db94  call    _XcptFilter_0
0x18002db99  mov     [rbp+0A0h], eax
0x18002db9f  jmp     short loc_18002DBAB
0x18002dba1  mov     dword ptr [rbp+0A0h], 0
0x18002dbab  mov     eax, [rbp+0A0h]
0x18002dbb1  add     rsp, 20h
0x18002dbb5  pop     rbp
0x18002dbb6  retn
0x18002dbb8  push    rbp
0x18002dbba  sub     rsp, 20h
0x18002dbbe  mov     rbp, rdx
0x18002dbc1  cmp     dword ptr [rbp+118h], 1
0x18002dbc8  ja      short loc_18002DBD4
0x18002dbca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
