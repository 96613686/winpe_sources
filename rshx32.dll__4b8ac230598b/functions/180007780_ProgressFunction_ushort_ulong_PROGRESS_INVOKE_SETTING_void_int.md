# ProgressFunction(ushort *,ulong,_PROGRESS_INVOKE_SETTING *,void *,int)

- ea: `0x180007780`
- end: `0x180007944`
- name: `?ProgressFunction@@YAXPEAGKPEAW4_PROGRESS_INVOKE_SETTING@@PEAXH@Z`
- size: `452`
- prototype: `void __fastcall(const unsigned __int16 *pObjectName, signed int Status, PPROG_INVOKE_SETTING pInvokeSetting, _QWORD *Args, BOOL SecuritySet)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000729c`
- `0x180007780`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x1800077e5`
- `SHELL32!SHChangeNotify` at `0x1800077e5`
- `USER32!DialogBoxParamW` at `0x1800078a0`
- `USER32!DialogBoxParamW` at `0x1800078a0`
- `USER32!SetForegroundWindow` at `0x18000787b`
- `USER32!SetForegroundWindow` at `0x18000787b`
- `USER32!IsWindowVisible` at `0x180007860`
- `USER32!IsWindowVisible` at `0x180007860`
- `USER32!ShowWindow` at `0x180007871`
- `USER32!ShowWindow` at `0x180007871`

## pseudocode

```c
void __fastcall ProgressFunction(
        const unsigned __int16 *pObjectName,
        signed int Status,
        PPROG_INVOKE_SETTING pInvokeSetting,
        _QWORD *Args,
        BOOL SecuritySet)
{
  signed int v7; // edi
  __int64 v9; // r15
  void *v10; // r8
  __int64 v11; // rax
  HWND v12; // rcx
  HWND v13; // rdi
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // [rsp+30h] [rbp-38h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-30h] BYREF
  signed int v19; // [rsp+40h] [rbp-28h]
  int v20; // [rsp+44h] [rbp-24h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-20h]
  __int64 v22; // [rsp+50h] [rbp-18h]

  if ( Args )
  {
    v7 = Status;
    if ( pObjectName )
    {
      v9 = Args[1];
      if ( Status )
      {
        if ( SecuritySet )
        {
          if ( (*(_BYTE *)Args & 1) != 0 )
          {
            v10 = (void *)Args[2];
            v17 = 0;
            if ( !(unsigned int)CNTFSSecurity::GiveOwnerFullControl((HWND *)v9, pObjectName, v10, &v17) )
            {
              *pInvokeSetting = (v17 != 0) + 5;
              return;
            }
          }
        }
        v11 = Args[1];
        v12 = *(HWND *)(v11 + 328);
        hWnd = v12;
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        v19 = v7;
        v20 = 0;
        v22 = 0;
        v21 = pObjectName;
        v13 = *(HWND *)(v11 + 328);
        if ( !IsWindowVisible(v12) )
        {
          ShowWindow(hWnd, 5);
          SetForegroundWindow(hWnd);
        }
        if ( (unsigned int)DialogBoxParamW(
                             g_hInstance,
                             (LPCWSTR)1,
                             v13,
                             (DLGPROC)FailedApplySecurityProc,
                             (LPARAM)&hWnd) == 1 )
        {
          *pInvokeSetting = ProgressInvokePrePostError;
        }
        else
        {
          *pInvokeSetting = ProgressCancelOperation;
          *((_DWORD *)Args + 6) = 1;
        }
      }
      else
      {
        if ( !SecuritySet )
          return;
        if ( (*(_BYTE *)Args & 4) != 0 )
          SHChangeNotify(4096, 0x3005u, pObjectName, 0);
      }
      v14 = *(_QWORD *)(v9 + 320);
      if ( v14 )
      {
        v15 = *(_DWORD *)(v9 + 628);
        if ( v15 >= 0x14 )
        {
          (*(void (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v14 + 80LL))(
            v14,
            2,
            pObjectName);
          v16 = 0;
        }
        else
        {
          v16 = v15 + 1;
        }
        *(_DWORD *)(v9 + 628) = v16;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 320) + 56LL))(*(_QWORD *)(v9 + 320)) )
        {
          *pInvokeSetting = ProgressCancelOperation;
          *((_DWORD *)Args + 6) = 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180007780  test    r9, r9
0x180007783  jz      locret_180007943
0x180007789  push    rbp
0x18000778a  push    rbx
0x18000778b  push    rsi
0x18000778c  push    rdi
0x18000778d  push    r14
0x18000778f  push    r15
0x180007791  mov     rbp, rsp
0x180007794  sub     rsp, 68h
0x180007798  mov     rax, cs:__security_cookie
0x18000779f  xor     rax, rsp
0x1800077a2  mov     [rbp+var_10], rax
0x1800077a6  mov     rbx, r9
0x1800077a9  mov     rsi, r8
0x1800077ac  mov     edi, edx
0x1800077ae  mov     r14, rcx
0x1800077b1  test    rcx, rcx
0x1800077b4  jz      loc_18000792B
0x1800077ba  mov     r15, [r9+8]
0x1800077be  test    edx, edx
0x1800077c0  jnz     short loc_1800077F0
0x1800077c2  cmp     [rbp+SecuritySet], edx
0x1800077c5  jz      loc_18000792B
0x1800077cb  test    byte ptr [r9], 4
0x1800077cf  jz      loc_1800078C0
0x1800077d5  mov     r8, rcx; dwItem1
0x1800077d8  xor     r9d, r9d; dwItem2
0x1800077db  mov     ecx, 1000h; wEventId
0x1800077e0  mov     edx, 3005h; uFlags
0x1800077e5  call    cs:__imp_SHChangeNotify
0x1800077eb  jmp     loc_1800078C0
0x1800077f0  cmp     [rbp+SecuritySet], 0
0x1800077f4  jz      short loc_18000782D
0x1800077f6  test    byte ptr [r9], 1
0x1800077fa  jz      short loc_18000782D
0x1800077fc  mov     r8, [rbx+10h]; void *
0x180007800  lea     r9, [rbp+var_38]; int *
0x180007804  mov     rdx, r14; unsigned __int16 *
0x180007807  mov     [rbp+var_38], 0
0x18000780e  mov     rcx, r15; this
0x180007811  call    ?GiveOwnerFullControl@CNTFSSecurity@@QEAAJPEBGPEAXPEAH@Z; CNTFSSecurity::GiveOwnerFullControl(ushort const *,void *,int *)
0x180007816  test    eax, eax
0x180007818  jnz     short loc_18000782D
0x18000781a  mov     eax, [rbp+var_38]
0x18000781d  neg     eax
0x18000781f  sbb     ecx, ecx
0x180007821  neg     ecx
0x180007823  add     ecx, 5
0x180007826  mov     [rsi], ecx
0x180007828  jmp     loc_18000792B
0x18000782d  mov     rax, [rbx+8]
0x180007831  mov     rcx, [rax+148h]; hWnd
0x180007838  mov     [rbp+hWnd], rcx
0x18000783c  test    edi, edi
0x18000783e  jle     short loc_180007849
0x180007840  movzx   edi, di
0x180007843  or      edi, 80070000h
0x180007849  xor     edx, edx
0x18000784b  mov     [rbp+var_28], edi
0x18000784e  mov     [rbp+var_24], edx
0x180007851  mov     [rbp+var_18], rdx
0x180007855  mov     [rbp+var_20], r14
0x180007859  mov     rdi, [rax+148h]
0x180007860  call    cs:__imp_IsWindowVisible
0x180007866  test    eax, eax
0x180007868  jnz     short loc_180007881
0x18000786a  mov     rcx, [rbp+hWnd]; hWnd
0x18000786e  lea     edx, [rax+5]; nCmdShow
0x180007871  call    cs:__imp_ShowWindow
0x180007877  mov     rcx, [rbp+hWnd]; hWnd
0x18000787b  call    cs:__imp_SetForegroundWindow
0x180007881  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180007888  lea     rax, [rbp+hWnd]
0x18000788c  lea     r9, ?FailedApplySecurityProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180007893  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x180007898  mov     r8, rdi; hWndParent
0x18000789b  mov     edx, 1; lpTemplateName
0x1800078a0  call    cs:__imp_DialogBoxParamW
0x1800078a6  cmp     eax, 1
0x1800078a9  jz      short loc_1800078BA
0x1800078ab  mov     dword ptr [rsi], 4
0x1800078b1  mov     dword ptr [rbx+18h], 1
0x1800078b8  jmp     short loc_1800078C0
0x1800078ba  mov     dword ptr [rsi], 6
0x1800078c0  mov     rcx, [r15+140h]
0x1800078c7  test    rcx, rcx
0x1800078ca  jz      short loc_18000792B
0x1800078cc  mov     eax, [r15+274h]
0x1800078d3  cmp     eax, 14h
0x1800078d6  jnb     short loc_1800078DC
0x1800078d8  inc     eax
0x1800078da  jmp     short loc_180007900
0x1800078dc  mov     rax, [rcx]
0x1800078df  mov     r9d, 1
0x1800078e5  mov     r8, r14
0x1800078e8  mov     [rsp+68h+dwInitParam], 0
0x1800078f1  mov     rax, [rax+50h]
0x1800078f5  lea     edx, [r9+1]
0x1800078f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fe  xor     eax, eax
0x180007900  mov     [r15+274h], eax
0x180007907  mov     rcx, [r15+140h]
0x18000790e  mov     rax, [rcx]
0x180007911  mov     rax, [rax+38h]
0x180007915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000791a  test    eax, eax
0x18000791c  jz      short loc_18000792B
0x18000791e  mov     dword ptr [rsi], 4
0x180007924  mov     dword ptr [rbx+18h], 1
0x18000792b  mov     rcx, [rbp+var_10]
0x18000792f  xor     rcx, rsp; StackCookie
0x180007932  call    __security_check_cookie
0x180007937  add     rsp, 68h
0x18000793b  pop     r15
0x18000793d  pop     r14
0x18000793f  pop     rdi
0x180007940  pop     rsi
0x180007941  pop     rbx
0x180007942  pop     rbp
0x180007943  retn
```
