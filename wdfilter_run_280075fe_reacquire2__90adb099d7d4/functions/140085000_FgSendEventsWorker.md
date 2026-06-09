# FgSendEventsWorker

- ea: `0x140085000`
- end: `0x1400854f8`
- name: `FgSendEventsWorker`
- size: `1272`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140003460`
- `0x140003950`
- `0x140004754`
- `0x1400051bc`
- `0x1400118d0`
- `0x140034b50`
- `0x140035080`
- `0x140035e50`
- `0x140066180`
- `0x140085000`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085275`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14008546a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085275`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14008546a`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085088`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085178`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400852ad`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14008549c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085088`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085178`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400852ad`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14008549c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008528f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008547e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008528f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008547e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140085051`
- `ntoskrnl!ExAcquireFastMutex` at `0x140085051`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008506e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008506e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400854c6`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400854c6`

## pseudocode

```c
void __fastcall FgSendEventsWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, char *Context)
{
  char v3; // al
  unsigned int v4; // edi
  unsigned int v5; // r14d
  struct _FLT_GENERIC_WORKITEM *v7; // r15
  struct _FAST_MUTEX *v8; // rbx
  struct _RTL_AVL_TABLE *v9; // rsi
  BOOLEAN i; // dl
  _QWORD *v11; // rax
  unsigned int v12; // edx
  unsigned int v13; // r8d
  unsigned __int16 *v14; // rcx
  unsigned int v15; // ecx
  unsigned int v16; // r15d
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdi
  int Notification; // eax
  _DWORD *v20; // rbx
  __int64 v21; // rdx
  const UNICODE_STRING **v22; // rax
  unsigned int j; // r13d
  const UNICODE_STRING **v24; // r14
  const UNICODE_STRING *v25; // rbp
  unsigned __int64 v26; // r12
  NTSTATUS v27; // r8d
  unsigned __int64 v28; // rcx
  __int64 v29; // rdx
  void *v30; // rbx
  __int64 v31; // rdi
  _QWORD *v32; // rax
  int v33; // [rsp+20h] [rbp-68h]
  PVOID P[2]; // [rsp+38h] [rbp-50h] BYREF

  v3 = Context[512];
  v4 = 0;
  v5 = 0;
  P[0] = 0;
  v7 = FltWorkItem;
  if ( v3 )
    goto LABEL_65;
  v8 = (struct _FAST_MUTEX *)(Context + 272);
  ExAcquireFastMutex((PFAST_MUTEX)(Context + 272));
  v9 = (struct _RTL_AVL_TABLE *)*((_QWORD *)Context + 33);
  *((_QWORD *)Context + 33) = 0;
  ExReleaseFastMutex(v8);
  if ( !v9 )
    goto LABEL_65;
  for ( i = 1; ; i = 0 )
  {
    v11 = RtlEnumerateGenericTableAvl(v9, i);
    if ( !v11 )
      break;
    ++v5;
    v12 = v4 + 64;
    if ( v4 + 64 < v4 )
      goto LABEL_63;
    v13 = v12 + *((unsigned __int16 *)v11 + 20);
    if ( v13 < v12 )
      goto LABEL_63;
    v4 = v13 + 2;
    if ( v13 + 2 < v13 )
      goto LABEL_63;
    v14 = (unsigned __int16 *)v11[3];
    if ( v14 )
    {
      v15 = v4 + *v14;
      if ( v15 < v4 )
        goto LABEL_63;
      v4 = v15 + 2;
      if ( v15 + 2 < v15 )
        goto LABEL_63;
    }
  }
  v16 = v4 + 32;
  if ( v4 + 32 >= v4 )
  {
    v17 = (unsigned __int64)v5 << 6;
    P[1] = 0;
    if ( is_mul_ok(v5, 0x40u) )
    {
      v18 = v17 + 32;
      if ( v17 + 32 >= v17 )
      {
        Notification = MpAsyncCreateNotification(P, v16);
        v20 = P[0];
        if ( Notification >= 0 )
        {
          *((_DWORD *)P[0] + 4) = 17;
          v20[2] = v16;
          v20[6] = v5;
          v22 = (const UNICODE_STRING **)RtlEnumerateGenericTableAvl(v9, 1u);
          for ( j = 0; ; ++j )
          {
            v24 = v22;
            if ( !v22 )
              break;
            v25 = v22[3];
            P[0] = (PVOID)v22[6];
            v26 = (unsigned __int64)j << 6;
            *(_DWORD *)((char *)v20 + v26 + 32) = *((_DWORD *)v22 + 2);
            *(_QWORD *)((char *)v20 + v26 + 36) = MpFileTimeToUlong64(v22[2]);
            *(_DWORD *)((char *)v20 + v26 + 44) = *((_DWORD *)v24 + 8);
            *((_BYTE *)v20 + v26 + 48) = *((_BYTE *)v24 + 56);
            *((_BYTE *)v20 + v26 + 49) = *((_BYTE *)v24 + 57);
            *(_OWORD *)((char *)v20 + v26 + 52) = *(_OWORD *)((char *)v24 + 60);
            *(_DWORD *)((char *)v20 + v26 + 68) = *((unsigned __int16 *)v24 + 20);
            *(_QWORD *)((char *)v20 + v26 + 72) = v18;
            v27 = RtlStringCbCopyUnicodeString(
                    (NTSTRSAFE_PWSTR)((char *)v20 + v18),
                    *((unsigned __int16 *)v24 + 20) + 2LL,
                    (PCUNICODE_STRING)(v24 + 5));
            if ( v27 < 0 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_51;
              }
              v21 = 37;
              goto LABEL_38;
            }
            v28 = v18 + *((unsigned __int16 *)v24 + 20) + 2LL;
            if ( v28 < v18 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v21 = 38;
                goto LABEL_34;
              }
              goto LABEL_51;
            }
            v18 += *((unsigned __int16 *)v24 + 20) + 2LL;
            if ( v25 )
            {
              *(_DWORD *)((char *)v20 + v26 + 80) = v25->Length;
              *(_QWORD *)((char *)v20 + v26 + 88) = v28;
              v27 = RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)((char *)v20 + v28), v25->Length + 2LL, v25);
              if ( v27 < 0 )
              {
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
                {
                  goto LABEL_51;
                }
                v21 = 39;
LABEL_38:
                v33 = v27;
                goto LABEL_50;
              }
              if ( v18 + v25->Length + 2LL < v18 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v21 = 40;
LABEL_34:
                  v33 = -1073741675;
                  goto LABEL_50;
                }
                goto LABEL_51;
              }
              v18 += v25->Length + 2LL;
            }
            if ( RtlDeleteElementGenericTableAvl(v9, v24) )
            {
              ExFreePoolWithTag(P[0], 0x6746504Du);
              if ( v25 )
                MpFreeString(v25);
            }
            v22 = (const UNICODE_STRING **)RtlEnumerateGenericTableAvl(v9, 1u);
          }
          _mm_lfence();
          Notification = MpAsyncSendNotification((_DWORD)v20, v16, 0, 1, 0);
          if ( Notification >= 0
            || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 41;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 36;
        }
        v33 = Notification;
LABEL_50:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v21,
          WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
          KeGetCurrentThread(),
          v33);
LABEL_51:
        if ( v20 )
          MpAsyncDereferenceNotification(v20);
        goto LABEL_60;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_60;
      v29 = 35;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_60;
      v29 = 34;
    }
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v29,
      WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
      KeGetCurrentThread(),
      -1073741675);
  }
LABEL_60:
  v7 = FltWorkItem;
LABEL_63:
  while ( 1 )
  {
    v32 = RtlEnumerateGenericTableAvl(v9, 1u);
    if ( !v32 )
      break;
    v30 = (void *)v32[6];
    v31 = v32[3];
    RtlDeleteElementGenericTableAvl(v9, v32);
    ExFreePoolWithTag(v30, 0x6746504Du);
    if ( v31 )
      MpFreeString(v31);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)DeferredContext + 3, v9);
LABEL_65:
  FltFreeGenericWorkItem(v7);
}

```

## disassembly

```asm
0x140085000  mov     [rsp+arg_8], rbx
0x140085005  push    rbp
0x140085006  push    rsi
0x140085007  push    rdi
0x140085008  push    r12
0x14008500a  push    r13
0x14008500c  push    r14
0x14008500e  push    r15
0x140085010  sub     rsp, 50h
0x140085014  mov     rax, cs:__security_cookie
0x14008501b  xor     rax, rsp
0x14008501e  mov     [rsp+88h+var_40], rax
0x140085023  mov     al, [r8+200h]
0x14008502a  xor     edi, edi
0x14008502c  xor     r14d, r14d
0x14008502f  mov     [rsp+88h+var_58], rcx
0x140085034  mov     [rsp+88h+P], rdi
0x140085039  mov     rbp, r8
0x14008503c  mov     r15, rcx
0x14008503f  test    al, al
0x140085041  jnz     loc_1400854C3
0x140085047  lea     rbx, [r8+110h]
0x14008504e  mov     rcx, rbx; FastMutex
0x140085051  call    cs:__imp_ExAcquireFastMutex
0x140085058  nop     dword ptr [rax+rax+00h]
0x14008505d  mov     rsi, [rbp+108h]
0x140085064  mov     rcx, rbx; FastMutex
0x140085067  mov     [rbp+108h], rdi
0x14008506e  call    cs:__imp_ExReleaseFastMutex
0x140085075  nop     dword ptr [rax+rax+00h]
0x14008507a  test    rsi, rsi
0x14008507d  jz      loc_1400854C3
0x140085083  mov     dl, 1; Restart
0x140085085  mov     rcx, rsi; Table
0x140085088  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14008508f  nop     dword ptr [rax+rax+00h]
0x140085094  test    rax, rax
0x140085097  jz      short loc_1400850EA
0x140085099  inc     r14d
0x14008509c  lea     edx, [rdi+40h]
0x14008509f  cmp     edx, edi
0x1400850a1  jb      loc_140085497
0x1400850a7  movzx   r8d, word ptr [rax+28h]
0x1400850ac  add     r8d, edx
0x1400850af  cmp     r8d, edx
0x1400850b2  jb      loc_140085497
0x1400850b8  lea     edi, [r8+2]
0x1400850bc  cmp     edi, r8d
0x1400850bf  jb      loc_140085497
0x1400850c5  mov     rcx, [rax+18h]
0x1400850c9  test    rcx, rcx
0x1400850cc  jz      short loc_1400850E6
0x1400850ce  movzx   ecx, word ptr [rcx]
0x1400850d1  add     ecx, edi
0x1400850d3  cmp     ecx, edi
0x1400850d5  jb      loc_140085497
0x1400850db  lea     edi, [rcx+2]
0x1400850de  cmp     edi, ecx
0x1400850e0  jb      loc_140085497
0x1400850e6  xor     edx, edx
0x1400850e8  jmp     short loc_140085085
0x1400850ea  lea     r15d, [rdi+20h]
0x1400850ee  cmp     r15d, edi
0x1400850f1  jb      loc_140085455
0x1400850f7  mov     ecx, r14d
0x1400850fa  mov     eax, 40h ; '@'
0x1400850ff  mul     rcx
0x140085102  mov     [rsp+88h+var_48], 0
0x14008510b  test    rdx, rdx
0x14008510e  jnz     loc_14008540B
0x140085114  lea     rdi, [rax+20h]
0x140085118  cmp     rdi, rax
0x14008511b  jb      loc_1400853EA
0x140085121  mov     edx, r15d
0x140085124  lea     rcx, [rsp+88h+P]
0x140085129  call    MpAsyncCreateNotification
0x14008512e  mov     rbx, [rsp+88h+P]
0x140085133  test    eax, eax
0x140085135  jns     short loc_140085164
0x140085137  mov     rdx, cs:WPP_GLOBAL_Control
0x14008513e  lea     rcx, WPP_GLOBAL_Control
0x140085145  cmp     rdx, rcx
0x140085148  jz      loc_1400853DB
0x14008514e  mov     ecx, [rdx+2Ch]
0x140085151  test    cl, 1
0x140085154  jz      loc_1400853DB
0x14008515a  mov     edx, 24h ; '$'
0x14008515f  jmp     loc_1400853B4
0x140085164  mov     dword ptr [rbx+10h], 11h
0x14008516b  mov     dl, 1; Restart
0x14008516d  mov     [rbx+8], r15d
0x140085171  mov     rcx, rsi; Table
0x140085174  mov     [rbx+18h], r14d
0x140085178  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14008517f  nop     dword ptr [rax+rax+00h]
0x140085184  xor     r13d, r13d
0x140085187  mov     r14, rax
0x14008518a  test    rax, rax
0x14008518d  jz      loc_140085370
0x140085193  mov     rax, [rax+30h]
0x140085197  mov     rbp, [r14+18h]
0x14008519b  mov     [rsp+88h+P], rax
0x1400851a0  mov     eax, [r14+8]
0x1400851a4  mov     r12d, r13d
0x1400851a7  shl     r12, 6
0x1400851ab  mov     [r12+rbx+20h], eax
0x1400851b0  mov     rcx, [r14+10h]
0x1400851b4  call    MpFileTimeToUlong64
0x1400851b9  mov     [r12+rbx+24h], rax
0x1400851be  lea     r8, [r14+28h]; SourceString
0x1400851c2  mov     eax, [r14+20h]
0x1400851c6  lea     rcx, [rdi+rbx]; pszDest
0x1400851ca  mov     [r12+rbx+2Ch], eax
0x1400851cf  mov     al, [r14+38h]
0x1400851d3  mov     [r12+rbx+30h], al
0x1400851d8  mov     al, [r14+39h]
0x1400851dc  mov     [r12+rbx+31h], al
0x1400851e1  movups  xmm0, xmmword ptr [r14+3Ch]
0x1400851e6  movdqu  xmmword ptr [r12+rbx+34h], xmm0
0x1400851ed  movzx   eax, word ptr [r8]
0x1400851f1  mov     [r12+rbx+44h], eax
0x1400851f6  mov     [r12+rbx+48h], rdi
0x1400851fb  movzx   edx, word ptr [r8]
0x1400851ff  add     rdx, 2; cbDest
0x140085203  call    RtlStringCbCopyUnicodeString
0x140085208  mov     r8d, eax
0x14008520b  test    eax, eax
0x14008520d  js      loc_14008534F
0x140085213  movzx   ecx, word ptr [r14+28h]
0x140085218  add     rcx, 2
0x14008521c  add     rcx, rdi
0x14008521f  cmp     rcx, rdi
0x140085222  jb      loc_140085326
0x140085228  mov     rdi, rcx
0x14008522b  test    rbp, rbp
0x14008522e  jz      short loc_14008526F
0x140085230  movzx   eax, word ptr [rbp+0]
0x140085234  mov     r8, rbp; SourceString
0x140085237  mov     [r12+rbx+50h], eax
0x14008523c  mov     [r12+rbx+58h], rcx
0x140085241  add     rcx, rbx; pszDest
0x140085244  movzx   edx, word ptr [rbp+0]
0x140085248  add     rdx, 2; cbDest
0x14008524c  call    RtlStringCbCopyUnicodeString
0x140085251  mov     r8d, eax
0x140085254  test    eax, eax
0x140085256  js      loc_1400852F5
0x14008525c  movzx   edx, word ptr [rbp+0]
0x140085260  add     rdx, 2
0x140085264  add     rdx, rdi
0x140085267  cmp     rdx, rdi
0x14008526a  jb      short loc_1400852C1
0x14008526c  mov     rdi, rdx
0x14008526f  mov     rdx, r14; Buffer
0x140085272  mov     rcx, rsi; Table
0x140085275  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14008527c  nop     dword ptr [rax+rax+00h]
0x140085281  test    al, al
0x140085283  jz      short loc_1400852A8
0x140085285  mov     rcx, [rsp+88h+P]; P
0x14008528a  mov     edx, 6746504Dh; Tag
0x14008528f  call    cs:__imp_ExFreePoolWithTag
0x140085296  nop     dword ptr [rax+rax+00h]
0x14008529b  test    rbp, rbp
0x14008529e  jz      short loc_1400852A8
0x1400852a0  mov     rcx, rbp
0x1400852a3  call    MpFreeString
0x1400852a8  mov     dl, 1; Restart
0x1400852aa  mov     rcx, rsi; Table
0x1400852ad  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400852b4  nop     dword ptr [rax+rax+00h]
0x1400852b9  inc     r13d
0x1400852bc  jmp     loc_140085187
0x1400852c1  mov     rax, cs:WPP_GLOBAL_Control
0x1400852c8  lea     rcx, WPP_GLOBAL_Control
0x1400852cf  cmp     rax, rcx
0x1400852d2  jz      loc_1400853DB
0x1400852d8  mov     eax, [rax+2Ch]
0x1400852db  test    al, 1
0x1400852dd  jz      loc_1400853DB
0x1400852e3  mov     edx, 28h ; '('
0x1400852e8  mov     [rsp+88h+var_68], 0C0000095h
0x1400852f0  jmp     loc_1400853B8
0x1400852f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400852fc  lea     rcx, WPP_GLOBAL_Control
0x140085303  cmp     rax, rcx
0x140085306  jz      loc_1400853DB
0x14008530c  mov     eax, [rax+2Ch]
0x14008530f  test    al, 1
0x140085311  jz      loc_1400853DB
0x140085317  mov     edx, 27h ; '''
0x14008531c  mov     [rsp+88h+var_68], r8d
0x140085321  jmp     loc_1400853B8
0x140085326  mov     rax, cs:WPP_GLOBAL_Control
0x14008532d  lea     rcx, WPP_GLOBAL_Control
0x140085334  cmp     rax, rcx
0x140085337  jz      loc_1400853DB
0x14008533d  mov     eax, [rax+2Ch]
0x140085340  test    al, 1
0x140085342  jz      loc_1400853DB
0x140085348  mov     edx, 26h ; '&'
0x14008534d  jmp     short loc_1400852E8
0x14008534f  mov     rax, cs:WPP_GLOBAL_Control
0x140085356  lea     rcx, WPP_GLOBAL_Control
0x14008535d  cmp     rax, rcx
0x140085360  jz      short loc_1400853DB
0x140085362  mov     eax, [rax+2Ch]
0x140085365  test    al, 1
0x140085367  jz      short loc_1400853DB
0x140085369  mov     edx, 25h ; '%'
0x14008536e  jmp     short loc_14008531C
0x140085370  lfence
0x140085373  mov     r9d, 1
0x140085379  mov     qword ptr [rsp+88h+var_68], 0
0x140085382  xor     r8d, r8d
0x140085385  mov     edx, r15d
0x140085388  mov     rcx, rbx
0x14008538b  call    MpAsyncSendNotification
0x140085390  test    eax, eax
0x140085392  jns     short loc_1400853DB
0x140085394  mov     rdx, cs:WPP_GLOBAL_Control
0x14008539b  lea     rcx, WPP_GLOBAL_Control
0x1400853a2  cmp     rdx, rcx
0x1400853a5  jz      short loc_1400853DB
0x1400853a7  mov     ecx, [rdx+2Ch]
0x1400853aa  test    cl, 1
0x1400853ad  jz      short loc_1400853DB
0x1400853af  mov     edx, 29h ; ')'
0x1400853b4  mov     [rsp+88h+var_68], eax
0x1400853b8  lfence
0x1400853bb  mov     r9, gs:188h
0x1400853c4  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x1400853cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400853d2  mov     rcx, [rcx+18h]
0x1400853d6  call    WPP_SF_qD
0x1400853db  test    rbx, rbx
0x1400853de  jz      short loc_140085455
0x1400853e0  mov     rcx, rbx
0x1400853e3  call    MpAsyncDereferenceNotification
0x1400853e8  jmp     short loc_140085455
0x1400853ea  mov     rax, cs:WPP_GLOBAL_Control
0x1400853f1  lea     rcx, WPP_GLOBAL_Control
0x1400853f8  cmp     rax, rcx
0x1400853fb  jz      short loc_140085455
0x1400853fd  mov     eax, [rax+2Ch]
0x140085400  test    al, 1
0x140085402  jz      short loc_140085455
0x140085404  mov     edx, 23h ; '#'
0x140085409  jmp     short loc_14008542A
0x14008540b  mov     rax, cs:WPP_GLOBAL_Control
0x140085412  lea     rcx, WPP_GLOBAL_Control
0x140085419  cmp     rax, rcx
0x14008541c  jz      short loc_140085455
0x14008541e  mov     eax, [rax+2Ch]
0x140085421  test    al, 1
0x140085423  jz      short loc_140085455
0x140085425  mov     edx, 22h ; '"'
0x14008542a  lfence
0x14008542d  mov     r9, gs:188h
0x140085436  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x14008543d  mov     rcx, cs:WPP_GLOBAL_Control
0x140085444  mov     [rsp+88h+var_68], 0C0000095h
0x14008544c  mov     rcx, [rcx+18h]
0x140085450  call    WPP_SF_qD
0x140085455  mov     r15, [rsp+88h+var_58]
0x14008545a  jmp     short loc_140085497
0x14008545c  mov     rbx, [rax+30h]
0x140085460  mov     rdx, rax; Buffer
0x140085463  mov     rdi, [rax+18h]
0x140085467  mov     rcx, rsi; Table
0x14008546a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140085471  nop     dword ptr [rax+rax+00h]
0x140085476  mov     edx, 6746504Dh; Tag
0x14008547b  mov     rcx, rbx; P
0x14008547e  call    cs:__imp_ExFreePoolWithTag
0x140085485  nop     dword ptr [rax+rax+00h]
0x14008548a  test    rdi, rdi
0x14008548d  jz      short loc_140085497
0x14008548f  mov     rcx, rdi
0x140085492  call    MpFreeString
0x140085497  mov     dl, 1; Restart
0x140085499  mov     rcx, rsi; Table
0x14008549c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400854a3  nop     dword ptr [rax+rax+00h]
0x1400854a8  test    rax, rax
0x1400854ab  jnz     short loc_14008545C
0x1400854ad  mov     rcx, cs:DeferredContext
0x1400854b4  mov     rdx, rsi; Entry
0x1400854b7  add     rcx, 180h; Lookaside
0x1400854be  call    ExFreeToNPagedLookasideList
0x1400854c3  mov     rcx, r15; FltWorkItem
0x1400854c6  call    cs:__imp_FltFreeGenericWorkItem
0x1400854cd  nop     dword ptr [rax+rax+00h]
0x1400854d2  mov     rcx, [rsp+88h+var_40]
0x1400854d7  xor     rcx, rsp; StackCookie
0x1400854da  call    __security_check_cookie
0x1400854df  mov     rbx, [rsp+88h+arg_8]
0x1400854e7  add     rsp, 50h
0x1400854eb  pop     r15
0x1400854ed  pop     r14
  ... truncated ...
```
