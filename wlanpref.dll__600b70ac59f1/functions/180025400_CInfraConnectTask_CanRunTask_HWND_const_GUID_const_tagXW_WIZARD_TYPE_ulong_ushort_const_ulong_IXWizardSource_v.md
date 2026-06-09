# CInfraConnectTask::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180025400`
- end: `0x1800255c7`
- name: `?CanRunTask@CInfraConnectTask@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020800`
- `0x180023054`
- `0x180025400`
- `0x1800255d0`
- `0x18002d80e`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553b`

## pseudocode

```c
__int64 __fastcall CInfraConnectTask::CanRunTask(
        CInfraConnectTask *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  char *v11; // rax
  _DWORD *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 13, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
  }
  *((_QWORD *)a1 + 9) = a8;
  v11 = (char *)CoTaskMemAlloc(0x60u);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11 + 8, 0, 0x58u);
    *v12 = 96;
    v12[1] = 16388;
    *((_QWORD *)v12 + 2) = hModule;
    *((_QWORD *)v12 + 1) = a2;
    *((_QWORD *)v12 + 3) = 10408;
    *((_QWORD *)v12 + 4) = 10902;
    v13 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64))a1 + 9))(
            *((_QWORD *)a1 + 9),
            &IID_IXWizardPropertyBag,
            (__int64)a1 + 64);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 145)
        || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v16 = 14;
LABEL_16:
      WPP_SF_d(v15[17], v16, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids, (unsigned int)v13);
LABEL_17:
      CoTaskMemFree(v12);
      v12 = 0;
      goto LABEL_22;
    }
    v13 = CInfraConnectTask::InitializeTaskData(a1);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 145)
        || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v16 = 15;
      goto LABEL_16;
    }
  }
  else
  {
    v14 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
    }
  }
LABEL_22:
  *a9 = v12;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 17, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
  }
  return v14;
}

```

## disassembly

```asm
0x180025400  push    rbx
0x180025402  push    rsi
0x180025403  push    rdi
0x180025404  push    r14
0x180025406  push    r15
0x180025408  sub     rsp, 20h
0x18002540c  mov     rbx, rdx
0x18002540f  mov     rsi, rcx
0x180025412  mov     rcx, cs:WPP_GLOBAL_Control
0x180025419  lea     r14, WPP_GLOBAL_Control
0x180025420  lea     r15, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x180025427  cmp     rcx, r14
0x18002542a  jz      short loc_180025452
0x18002542c  cmp     byte ptr [rcx+91h], 4
0x180025433  jb      short loc_180025452
0x180025435  test    byte ptr [rcx+94h], 1
0x18002543c  jz      short loc_180025452
0x18002543e  mov     rcx, [rcx+88h]
0x180025445  mov     edx, 0Dh
0x18002544a  mov     r8, r15
0x18002544d  call    WPP_SF_
0x180025452  mov     rax, [rsp+48h+arg_38]
0x18002545a  mov     ecx, 60h ; '`'; cb
0x18002545f  mov     [rsi+48h], rax
0x180025463  call    cs:__imp_CoTaskMemAlloc
0x180025469  mov     rdi, rax
0x18002546c  test    rax, rax
0x18002546f  jz      loc_180025545
0x180025475  xor     edx, edx; Val
0x180025477  lea     rcx, [rax+8]; void *
0x18002547b  lea     r8d, [rdx+58h]; Size
0x18002547f  call    memset_0
0x180025484  mov     dword ptr [rdi], 60h ; '`'
0x18002548a  lea     r8, [rsi+40h]
0x18002548e  mov     dword ptr [rdi+4], 4004h
0x180025495  lea     rdx, IID_IXWizardPropertyBag
0x18002549c  mov     rcx, cs:hModule
0x1800254a3  mov     [rdi+10h], rcx
0x1800254a7  mov     [rdi+8], rbx
0x1800254ab  mov     qword ptr [rdi+18h], 28A8h
0x1800254b3  mov     qword ptr [rdi+20h], 2A96h
0x1800254bb  mov     rcx, [rsi+48h]
0x1800254bf  mov     rax, [rcx]
0x1800254c2  mov     rax, [rax]
0x1800254c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254ca  mov     ebx, eax
0x1800254cc  test    eax, eax
0x1800254ce  jns     short loc_1800254F5
0x1800254d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254d7  cmp     rcx, r14
0x1800254da  jz      short loc_180025538
0x1800254dc  cmp     byte ptr [rcx+91h], 1
0x1800254e3  jb      short loc_180025538
0x1800254e5  test    byte ptr [rcx+94h], 1
0x1800254ec  jz      short loc_180025538
0x1800254ee  mov     edx, 0Eh
0x1800254f3  jmp     short loc_180025526
0x1800254f5  mov     rcx, rsi; this
0x1800254f8  call    ?InitializeTaskData@CInfraConnectTask@@AEAAJXZ; CInfraConnectTask::InitializeTaskData(void)
0x1800254fd  mov     ebx, eax
0x1800254ff  test    eax, eax
0x180025501  jns     short loc_18002557C
0x180025503  mov     rcx, cs:WPP_GLOBAL_Control
0x18002550a  cmp     rcx, r14
0x18002550d  jz      short loc_180025538
0x18002550f  cmp     byte ptr [rcx+91h], 1
0x180025516  jb      short loc_180025538
0x180025518  test    byte ptr [rcx+94h], 1
0x18002551f  jz      short loc_180025538
0x180025521  mov     edx, 0Fh
0x180025526  mov     rcx, [rcx+88h]
0x18002552d  mov     r9d, eax
0x180025530  mov     r8, r15
0x180025533  call    WPP_SF_d
0x180025538  mov     rcx, rdi; pv
0x18002553b  call    cs:__imp_CoTaskMemFree
0x180025541  xor     edi, edi
0x180025543  jmp     short loc_18002557C
0x180025545  mov     ebx, 8007000Eh
0x18002554a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025551  cmp     rcx, r14
0x180025554  jz      short loc_18002557C
0x180025556  cmp     byte ptr [rcx+91h], 1
0x18002555d  jb      short loc_18002557C
0x18002555f  test    byte ptr [rcx+94h], 1
0x180025566  jz      short loc_18002557C
0x180025568  mov     rcx, [rcx+88h]
0x18002556f  mov     edx, 10h
0x180025574  mov     r8, r15
0x180025577  call    WPP_SF_
0x18002557c  mov     rax, [rsp+48h+arg_40]
0x180025584  mov     [rax], rdi
0x180025587  mov     rcx, cs:WPP_GLOBAL_Control
0x18002558e  cmp     rcx, r14
0x180025591  jz      short loc_1800255B9
0x180025593  cmp     byte ptr [rcx+91h], 4
0x18002559a  jb      short loc_1800255B9
0x18002559c  test    byte ptr [rcx+94h], 1
0x1800255a3  jz      short loc_1800255B9
0x1800255a5  mov     rcx, [rcx+88h]
0x1800255ac  mov     edx, 11h
0x1800255b1  mov     r8, r15
0x1800255b4  call    WPP_SF_
0x1800255b9  mov     eax, ebx
0x1800255bb  add     rsp, 20h
0x1800255bf  pop     r15
0x1800255c1  pop     r14
0x1800255c3  pop     rdi
0x1800255c4  pop     rsi
0x1800255c5  pop     rbx
0x1800255c6  retn
```
