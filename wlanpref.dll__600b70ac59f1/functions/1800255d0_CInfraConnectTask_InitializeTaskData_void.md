# CInfraConnectTask::InitializeTaskData(void)

- ea: `0x1800255d0`
- end: `0x18002576e`
- name: `?InitializeTaskData@CInfraConnectTask@@AEAAJXZ`
- size: `414`
- prototype: `__int64 __fastcall(CInfraConnectTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180025400`

## callees

- `0x1800012e8`
- `0x180020800`
- `0x180023054`
- `0x1800255d0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CInfraConnectTask::InitializeTaskData(CInfraConnectTask *this)
{
  __int64 v2; // rcx
  unsigned int v3; // eax
  int v4; // ebx
  _QWORD *v5; // rcx
  _OWORD *v6; // rax
  char *v7; // rbx
  int v8; // eax
  void *Block; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 18, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
  }
  v2 = *((_QWORD *)this + 8);
  Block = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, void **, _QWORD))(*(_QWORD *)v2 + 48LL))(
         v2,
         0,
         L"_user_context_handle",
         &Block,
         0);
  v4 = v3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 19, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids, v3);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v4 != 1 )
  {
    if ( v4 < 0 )
      return (unsigned int)v4;
    goto LABEL_16;
  }
  v6 = Block;
  if ( !Block )
  {
LABEL_19:
    v7 = 0;
    goto LABEL_20;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 145) >= 4u && (*((_BYTE *)v5 + 148) & 1) != 0 )
  {
    WPP_SF_(v5[17], 20, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
LABEL_16:
    v6 = Block;
  }
  if ( !v6 )
    goto LABEL_19;
  v7 = (char *)this + 80;
  *((_OWORD *)this + 5) = *v6;
  operator delete(v6);
LABEL_20:
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, char *, int))(**((_QWORD **)this + 8) + 40LL))(
         *((_QWORD *)this + 8),
         0,
         L"ConnectionGuid",
         v7,
         2);
  v4 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145)
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      21,
      WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids,
      (unsigned int)v8);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800255d0  mov     [rsp+arg_8], rbx
0x1800255d5  mov     [rsp+arg_10], rdi
0x1800255da  push    r15
0x1800255dc  sub     rsp, 30h
0x1800255e0  mov     rdi, rcx
0x1800255e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255ea  lea     r15, WPP_GLOBAL_Control
0x1800255f1  cmp     rcx, r15
0x1800255f4  jz      short loc_180025620
0x1800255f6  cmp     byte ptr [rcx+91h], 4
0x1800255fd  jb      short loc_180025620
0x1800255ff  test    byte ptr [rcx+94h], 1
0x180025606  jz      short loc_180025620
0x180025608  mov     rcx, [rcx+88h]
0x18002560f  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x180025616  mov     edx, 12h
0x18002561b  call    WPP_SF_
0x180025620  mov     rcx, [rdi+40h]
0x180025624  lea     r9, [rsp+38h+Block]
0x180025629  mov     [rsp+38h+Block], 0
0x180025632  lea     r8, aUserContextHan; "_user_context_handle"
0x180025639  xor     edx, edx
0x18002563b  mov     [rsp+38h+var_18], 0
0x180025644  mov     rax, [rcx]
0x180025647  mov     rax, [rax+30h]
0x18002564b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025650  mov     ebx, eax
0x180025652  mov     rcx, cs:WPP_GLOBAL_Control
0x180025659  cmp     rcx, r15
0x18002565c  jz      short loc_180025692
0x18002565e  cmp     byte ptr [rcx+91h], 4
0x180025665  jb      short loc_180025692
0x180025667  test    byte ptr [rcx+94h], 1
0x18002566e  jz      short loc_180025692
0x180025670  mov     rcx, [rcx+88h]
0x180025677  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x18002567e  mov     edx, 13h
0x180025683  mov     r9d, eax
0x180025686  call    WPP_SF_d
0x18002568b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025692  cmp     ebx, 1
0x180025695  jnz     short loc_1800256CF
0x180025697  mov     rax, [rsp+38h+Block]
0x18002569c  test    rax, rax
0x18002569f  jz      short loc_1800256F6
0x1800256a1  cmp     rcx, r15
0x1800256a4  jz      short loc_1800256DC
0x1800256a6  cmp     byte ptr [rcx+91h], 4
0x1800256ad  jb      short loc_1800256DC
0x1800256af  test    [rcx+94h], bl
0x1800256b5  jz      short loc_1800256DC
0x1800256b7  mov     rcx, [rcx+88h]
0x1800256be  lea     edx, [rbx+13h]
0x1800256c1  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x1800256c8  call    WPP_SF_
0x1800256cd  jmp     short loc_1800256D7
0x1800256cf  test    ebx, ebx
0x1800256d1  js      loc_18002575B
0x1800256d7  mov     rax, [rsp+38h+Block]
0x1800256dc  test    rax, rax
0x1800256df  jz      short loc_1800256F6
0x1800256e1  movups  xmm0, xmmword ptr [rax]
0x1800256e4  lea     rbx, [rdi+50h]
0x1800256e8  mov     rcx, rax; Block
0x1800256eb  movdqu  xmmword ptr [rbx], xmm0
0x1800256ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800256f4  jmp     short loc_1800256F8
0x1800256f6  xor     ebx, ebx
0x1800256f8  mov     rcx, [rdi+40h]
0x1800256fc  lea     r8, aConnectionguid; "ConnectionGuid"
0x180025703  mov     r9, rbx
0x180025706  mov     dword ptr [rsp+38h+var_18], 2
0x18002570e  xor     edx, edx
0x180025710  mov     rax, [rcx]
0x180025713  mov     rax, [rax+28h]
0x180025717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002571c  mov     ebx, eax
0x18002571e  test    eax, eax
0x180025720  jns     short loc_18002575B
0x180025722  mov     rcx, cs:WPP_GLOBAL_Control
0x180025729  cmp     rcx, r15
0x18002572c  jz      short loc_18002575B
0x18002572e  cmp     byte ptr [rcx+91h], 1
0x180025735  jb      short loc_18002575B
0x180025737  test    byte ptr [rcx+94h], 1
0x18002573e  jz      short loc_18002575B
0x180025740  mov     rcx, [rcx+88h]
0x180025747  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x18002574e  mov     edx, 15h
0x180025753  mov     r9d, eax
0x180025756  call    WPP_SF_d
0x18002575b  mov     rdi, [rsp+38h+arg_10]
0x180025760  mov     eax, ebx
0x180025762  mov     rbx, [rsp+38h+arg_8]
0x180025767  add     rsp, 30h
0x18002576b  pop     r15
0x18002576d  retn
```
