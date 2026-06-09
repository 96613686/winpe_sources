# WaitForDeletion(SC_HANDLE__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ulong,ulong)

- ea: `0x140049f34`
- end: `0x14004a16b`
- name: `?WaitForDeletion@@YAKPEAUSC_HANDLE__@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KK@Z`
- size: `567`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140049b50`

## callees

- `0x14000c920`
- `0x14003f17c`
- `0x140047798`
- `0x140049f34`
- `0x14004a500`
- `0x14004a880`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x14004a039`
- `ADVAPI32!OpenServiceW` at `0x14004a039`
- `ADVAPI32!CloseServiceHandle` at `0x14004a07a`
- `ADVAPI32!CloseServiceHandle` at `0x14004a07a`
- `KERNEL32!GetTickCount` at `0x14004a0af`
- `KERNEL32!GetTickCount` at `0x14004a0e1`
- `KERNEL32!GetTickCount` at `0x14004a0af`
- `KERNEL32!GetTickCount` at `0x14004a0e1`
- `KERNEL32!Sleep` at `0x140049ffa`
- `KERNEL32!Sleep` at `0x140049ffa`

## pseudocode

```c
__int64 __fastcall WaitForDeletion(SC_HANDLE hSCManager, __int64 *a2, unsigned int a3)
{
  PVOID *v6; // r10
  unsigned int v7; // ebx
  int v8; // esi
  SC_HANDLE v9; // rdi
  DWORD TickCount; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)hSCManager, *a2, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  v8 = 1;
  if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 2) == 0 || *((_BYTE *)v6 + 25) < 5u )
    goto LABEL_10;
  WPP_SF_(v6[2], 43, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  while ( 1 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
    if ( !v8 )
      break;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
      WPP_SF_d(v6[2], 44, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, 500);
    Sleep(0x1F4u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
    }
    v9 = OpenServiceW(hSCManager, (LPCWSTR)*a2, 1u);
    if ( v9 )
    {
      v8 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
      CloseServiceHandle(v9);
    }
    else
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
    }
    if ( GetTickCount() - a3 > 0xEA60 )
    {
      v7 = 1460;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_38;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        TickCount = GetTickCount();
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids,
          a3,
          TickCount,
          60000);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      break;
    }
  }
  if ( v6 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v6 + 28) & 1) != 0
    && *((unsigned __int8 *)v6 + 25) >= (unsigned int)(v7 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v6[2], 49, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v7);
  }
LABEL_38:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(a2);
  return v7;
}

```

## disassembly

```asm
0x140049f34  push    rbx
0x140049f36  push    rbp
0x140049f37  push    rsi
0x140049f38  push    rdi
0x140049f39  push    r12
0x140049f3b  push    r14
0x140049f3d  push    r15
0x140049f3f  sub     rsp, 40h
0x140049f43  mov     ebp, r8d
0x140049f46  mov     r14, rdx
0x140049f49  mov     r15, rcx
0x140049f4c  mov     r10, cs:WPP_GLOBAL_Control
0x140049f53  lea     r12, WPP_GLOBAL_Control
0x140049f5a  cmp     r10, r12
0x140049f5d  jz      short loc_140049F8D
0x140049f5f  test    byte ptr [r10+1Ch], 1
0x140049f64  jz      short loc_140049F8D
0x140049f66  cmp     byte ptr [r10+19h], 5
0x140049f6b  jb      short loc_140049F8D
0x140049f6d  mov     rax, [rdx]
0x140049f70  mov     r9, rcx
0x140049f73  mov     rcx, [r10+10h]
0x140049f77  mov     [rsp+78h+var_50], r8d
0x140049f7c  mov     [rsp+78h+var_58], rax
0x140049f81  call    WPP_SF_qSDD
0x140049f86  mov     r10, cs:WPP_GLOBAL_Control
0x140049f8d  xor     ebx, ebx
0x140049f8f  lea     esi, [rbx+1]
0x140049f92  cmp     r10, r12
0x140049f95  jz      short loc_140049FBF
0x140049f97  test    byte ptr [r10+1Ch], 2
0x140049f9c  jz      short loc_140049FBF
0x140049f9e  cmp     byte ptr [r10+19h], 5
0x140049fa3  jb      short loc_140049FBF
0x140049fa5  mov     rcx, [r10+10h]
0x140049fa9  lea     edx, [rbx+2Bh]
0x140049fac  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140049fb3  call    WPP_SF_
0x140049fb8  mov     r10, cs:WPP_GLOBAL_Control
0x140049fbf  test    esi, esi
0x140049fc1  jz      loc_14004A119
0x140049fc7  cmp     r10, r12
0x140049fca  jz      short loc_140049FF5
0x140049fcc  test    byte ptr [r10+1Ch], 2
0x140049fd1  jz      short loc_140049FF5
0x140049fd3  cmp     byte ptr [r10+19h], 5
0x140049fd8  jb      short loc_140049FF5
0x140049fda  mov     rcx, [r10+10h]
0x140049fde  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140049fe5  mov     edx, 2Ch ; ','
0x140049fea  mov     r9d, 1F4h
0x140049ff0  call    WPP_SF_d
0x140049ff5  mov     ecx, 1F4h; dwMilliseconds
0x140049ffa  call    cs:__imp_Sleep
0x14004a000  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a007  cmp     rcx, r12
0x14004a00a  jz      short loc_14004A02D
0x14004a00c  test    byte ptr [rcx+1Ch], 2
0x14004a010  jz      short loc_14004A02D
0x14004a012  cmp     byte ptr [rcx+19h], 5
0x14004a016  jb      short loc_14004A02D
0x14004a018  mov     rcx, [rcx+10h]
0x14004a01c  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a023  mov     edx, 2Dh ; '-'
0x14004a028  call    WPP_SF_
0x14004a02d  mov     rdx, [r14]; lpServiceName
0x14004a030  mov     r8d, 1; dwDesiredAccess
0x14004a036  mov     rcx, r15; hSCManager
0x14004a039  call    cs:__imp_OpenServiceW
0x14004a03f  mov     rdi, rax
0x14004a042  test    rax, rax
0x14004a045  jz      short loc_14004A082
0x14004a047  mov     esi, 1
0x14004a04c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a053  cmp     rcx, r12
0x14004a056  jz      short loc_14004A077
0x14004a058  test    byte ptr [rcx+1Ch], 2
0x14004a05c  jz      short loc_14004A077
0x14004a05e  cmp     byte ptr [rcx+19h], 5
0x14004a062  jb      short loc_14004A077
0x14004a064  mov     rcx, [rcx+10h]
0x14004a068  lea     edx, [rsi+2Dh]
0x14004a06b  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a072  call    WPP_SF_
0x14004a077  mov     rcx, rdi; hSCObject
0x14004a07a  call    cs:__imp_CloseServiceHandle
0x14004a080  jmp     short loc_14004A0AF
0x14004a082  xor     esi, esi
0x14004a084  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a08b  cmp     rcx, r12
0x14004a08e  jz      short loc_14004A0AF
0x14004a090  test    byte ptr [rcx+1Ch], 2
0x14004a094  jz      short loc_14004A0AF
0x14004a096  cmp     byte ptr [rcx+19h], 5
0x14004a09a  jb      short loc_14004A0AF
0x14004a09c  mov     rcx, [rcx+10h]
0x14004a0a0  lea     edx, [rsi+2Fh]
0x14004a0a3  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a0aa  call    WPP_SF_
0x14004a0af  call    cs:__imp_GetTickCount
0x14004a0b5  sub     eax, ebp
0x14004a0b7  cmp     eax, 0EA60h
0x14004a0bc  jbe     loc_140049FB8
0x14004a0c2  mov     ebx, 5B4h
0x14004a0c7  mov     r10, cs:WPP_GLOBAL_Control
0x14004a0ce  cmp     r10, r12
0x14004a0d1  jz      short loc_14004A152
0x14004a0d3  test    byte ptr [r10+1Ch], 2
0x14004a0d8  jz      short loc_14004A119
0x14004a0da  cmp     byte ptr [r10+19h], 2
0x14004a0df  jb      short loc_14004A119
0x14004a0e1  call    cs:__imp_GetTickCount
0x14004a0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a0ee  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a0f5  mov     edx, 30h ; '0'
0x14004a0fa  mov     [rsp+78h+var_50], 0EA60h
0x14004a102  mov     r9d, ebp
0x14004a105  mov     dword ptr [rsp+78h+var_58], eax
0x14004a109  mov     rcx, [rcx+10h]
0x14004a10d  call    WPP_SF_DDd
0x14004a112  mov     r10, cs:WPP_GLOBAL_Control
0x14004a119  cmp     r10, r12
0x14004a11c  jz      short loc_14004A152
0x14004a11e  test    byte ptr [r10+1Ch], 1
0x14004a123  jz      short loc_14004A152
0x14004a125  movzx   edx, byte ptr [r10+19h]
0x14004a12a  mov     eax, ebx
0x14004a12c  neg     eax
0x14004a12e  sbb     ecx, ecx
0x14004a130  and     ecx, 0FFFFFFFDh
0x14004a133  add     ecx, 5
0x14004a136  cmp     edx, ecx
0x14004a138  jb      short loc_14004A152
0x14004a13a  mov     rcx, [r10+10h]
0x14004a13e  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a145  mov     edx, 31h ; '1'
0x14004a14a  mov     r9d, ebx
0x14004a14d  call    WPP_SF_d
0x14004a152  mov     rcx, r14
0x14004a155  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004a15a  mov     eax, ebx
0x14004a15c  add     rsp, 40h
0x14004a160  pop     r15
0x14004a162  pop     r14
0x14004a164  pop     r12
0x14004a166  pop     rdi
0x14004a167  pop     rsi
0x14004a168  pop     rbp
0x14004a169  pop     rbx
0x14004a16a  retn
```
