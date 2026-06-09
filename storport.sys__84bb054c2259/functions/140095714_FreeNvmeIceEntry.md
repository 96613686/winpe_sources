# FreeNvmeIceEntry

- ea: `0x140095714`
- end: `0x1400958e7`
- name: `FreeNvmeIceEntry`
- size: `467`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400950bc`
- `0x1400972c8`
- `0x14009f558`
- `0x1401900c4`

## callees

- `0x14000befc`
- `0x140095714`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140095793`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400957d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095819`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009583f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009585b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095873`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009588b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095793`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400957d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095819`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009583f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009585b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095873`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009588b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400958cd`
- `ntoskrnl!KeSweepLocalCaches` at `0x14009577f`
- `ntoskrnl!KeSweepLocalCaches` at `0x140095806`
- `ntoskrnl!KeSweepLocalCaches` at `0x14009577f`
- `ntoskrnl!KeSweepLocalCaches` at `0x140095806`

## pseudocode

```c
void __fastcall FreeNvmeIceEntry(PVOID P, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID v4; // rbx
  __int64 v5; // rbp
  __int64 v6; // rsi
  bool v7; // zf
  _BYTE *v8; // rax
  __int64 v9; // rcx
  _BYTE *i; // rax
  __int64 v11; // r14
  __int64 v12; // rcx
  __int64 v13; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx

  v4 = P;
  if ( *((_QWORD *)P + 10) )
  {
    v5 = 0;
    if ( *((_DWORD *)P + 16) )
    {
      do
      {
        v6 = *((_QWORD *)v4 + 10);
        v7 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(P, a2, a3, a4) == 0;
        v8 = *(_BYTE **)(v6 + 72 * v5 + 48);
        if ( v7 )
        {
          if ( v8 )
          {
            v9 = *((unsigned __int16 *)v8 + 2);
            for ( i = v8 + 16; v9; --v9 )
              *i++ = 0;
            KeSweepLocalCaches(v9);
            ExFreePoolWithTag(*(PVOID *)(v6 + 72 * v5 + 48), 0x72436152u);
            *(_QWORD *)(v6 + 72 * v5 + 48) = 0;
          }
        }
        else
        {
          v11 = v6 + 72 * v5;
          if ( v8 )
          {
            v12 = *(unsigned int *)(v11 + 40);
            if ( *(_DWORD *)(v11 + 40) )
            {
              do
              {
                *v8++ = 0;
                --v12;
              }
              while ( v12 );
            }
            P = *(PVOID *)(v6 + 72 * v5 + 48);
            if ( P )
            {
              ExFreePoolWithTag(P, 0x72436152u);
              *(_QWORD *)(v6 + 72 * v5 + 48) = 0;
            }
          }
          *(_DWORD *)(v11 + 40) = 0;
        }
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < *((_DWORD *)v4 + 16) );
    }
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(P, a2, a3, a4) )
      KeSweepLocalCaches(v13);
    ExFreePoolWithTag(*((PVOID *)v4 + 10), 0x72436152u);
    *((_QWORD *)v4 + 10) = 0;
  }
  IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                   P,
                                   a2,
                                   a3,
                                   a4);
  v15 = (void *)*((_QWORD *)v4 + 4);
  if ( !IsEnabledDeviceUsageNoInline )
  {
    ExFreePoolWithTag(v15, 0x53446152u);
    v16 = (void *)*((_QWORD *)v4 + 5);
LABEL_29:
    ExFreePoolWithTag(v16, 0x72436152u);
    goto LABEL_30;
  }
  if ( v15 )
    ExFreePoolWithTag(v15, 0x53446152u);
  v17 = (void *)*((_QWORD *)v4 + 7);
  if ( v17 )
    ExFreePoolWithTag(v17, 0x72436152u);
  v18 = (void *)*((_QWORD *)v4 + 6);
  if ( v18 )
    ExFreePoolWithTag(v18, 0x72436152u);
  v19 = (void *)*((_QWORD *)v4 + 5);
  if ( v19 )
    ExFreePoolWithTag(v19, 0x72436152u);
  v16 = (void *)*((_QWORD *)v4 + 14);
  if ( v16 )
    goto LABEL_29;
LABEL_30:
  ExFreePoolWithTag(v4, 0x72436152u);
}

```

## disassembly

```asm
0x140095714  push    rbx
0x140095716  push    rbp
0x140095717  push    rsi
0x140095718  push    rdi
0x140095719  push    r12
0x14009571b  push    r14
0x14009571d  sub     rsp, 28h
0x140095721  cmp     qword ptr [rcx+50h], 0
0x140095726  mov     rbx, rcx
0x140095729  mov     r12d, 72436152h
0x14009572f  jz      loc_14009582D
0x140095735  xor     ebp, ebp
0x140095737  cmp     [rcx+40h], ebp
0x14009573a  jbe     loc_1400957FD
0x140095740  mov     rsi, [rbx+50h]
0x140095744  lea     rdi, ds:0[rbp*8]
0x14009574c  add     rdi, rbp
0x14009574f  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140095754  test    eax, eax
0x140095756  mov     rax, [rsi+rdi*8+30h]
0x14009575b  jnz     short loc_1400957AA
0x14009575d  test    rax, rax
0x140095760  jz      loc_1400957F2
0x140095766  movzx   ecx, word ptr [rax+4]
0x14009576a  add     rax, 10h
0x14009576e  test    rcx, rcx
0x140095771  jz      short loc_14009577F
0x140095773  mov     byte ptr [rax], 0
0x140095776  inc     rax
0x140095779  sub     rcx, 1
0x14009577d  jnz     short loc_140095773
0x14009577f  call    cs:__imp_KeSweepLocalCaches
0x140095786  nop     dword ptr [rax+rax+00h]
0x14009578b  mov     rcx, [rsi+rdi*8+30h]; P
0x140095790  mov     edx, r12d; Tag
0x140095793  call    cs:__imp_ExFreePoolWithTag
0x14009579a  nop     dword ptr [rax+rax+00h]
0x14009579f  mov     qword ptr [rsi+rdi*8+30h], 0
0x1400957a8  jmp     short loc_1400957F2
0x1400957aa  lea     r14, [rsi+rdi*8]
0x1400957ae  test    rax, rax
0x1400957b1  jz      short loc_1400957EA
0x1400957b3  mov     ecx, [r14+28h]
0x1400957b7  test    rcx, rcx
0x1400957ba  jz      short loc_1400957C8
0x1400957bc  mov     byte ptr [rax], 0
0x1400957bf  inc     rax
0x1400957c2  sub     rcx, 1
0x1400957c6  jnz     short loc_1400957BC
0x1400957c8  mov     rcx, [rsi+rdi*8+30h]; P
0x1400957cd  test    rcx, rcx
0x1400957d0  jz      short loc_1400957EA
0x1400957d2  mov     edx, r12d; Tag
0x1400957d5  call    cs:__imp_ExFreePoolWithTag
0x1400957dc  nop     dword ptr [rax+rax+00h]
0x1400957e1  mov     qword ptr [rsi+rdi*8+30h], 0
0x1400957ea  mov     dword ptr [r14+28h], 0
0x1400957f2  inc     ebp
0x1400957f4  cmp     ebp, [rbx+40h]
0x1400957f7  jb      loc_140095740
0x1400957fd  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140095802  test    eax, eax
0x140095804  jz      short loc_140095812
0x140095806  call    cs:__imp_KeSweepLocalCaches
0x14009580d  nop     dword ptr [rax+rax+00h]
0x140095812  mov     rcx, [rbx+50h]; P
0x140095816  mov     edx, r12d; Tag
0x140095819  call    cs:__imp_ExFreePoolWithTag
0x140095820  nop     dword ptr [rax+rax+00h]
0x140095825  mov     qword ptr [rbx+50h], 0
0x14009582d  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140095832  mov     rcx, [rbx+20h]; P
0x140095836  test    eax, eax
0x140095838  jnz     short loc_140095851
0x14009583a  mov     edx, 53446152h; Tag
0x14009583f  call    cs:__imp_ExFreePoolWithTag
0x140095846  nop     dword ptr [rax+rax+00h]
0x14009584b  mov     rcx, [rbx+28h]
0x14009584f  jmp     short loc_1400958B8
0x140095851  test    rcx, rcx
0x140095854  jz      short loc_140095867
0x140095856  mov     edx, 53446152h; Tag
0x14009585b  call    cs:__imp_ExFreePoolWithTag
0x140095862  nop     dword ptr [rax+rax+00h]
0x140095867  mov     rcx, [rbx+38h]; P
0x14009586b  test    rcx, rcx
0x14009586e  jz      short loc_14009587F
0x140095870  mov     edx, r12d; Tag
0x140095873  call    cs:__imp_ExFreePoolWithTag
0x14009587a  nop     dword ptr [rax+rax+00h]
0x14009587f  mov     rcx, [rbx+30h]; P
0x140095883  test    rcx, rcx
0x140095886  jz      short loc_140095897
0x140095888  mov     edx, r12d; Tag
0x14009588b  call    cs:__imp_ExFreePoolWithTag
0x140095892  nop     dword ptr [rax+rax+00h]
0x140095897  mov     rcx, [rbx+28h]; P
0x14009589b  test    rcx, rcx
0x14009589e  jz      short loc_1400958AF
0x1400958a0  mov     edx, r12d; Tag
0x1400958a3  call    cs:__imp_ExFreePoolWithTag
0x1400958aa  nop     dword ptr [rax+rax+00h]
0x1400958af  mov     rcx, [rbx+70h]; P
0x1400958b3  test    rcx, rcx
0x1400958b6  jz      short loc_1400958C7
0x1400958b8  mov     edx, r12d; Tag
0x1400958bb  call    cs:__imp_ExFreePoolWithTag
0x1400958c2  nop     dword ptr [rax+rax+00h]
0x1400958c7  mov     edx, r12d; Tag
0x1400958ca  mov     rcx, rbx; P
0x1400958cd  call    cs:__imp_ExFreePoolWithTag
0x1400958d4  nop     dword ptr [rax+rax+00h]
0x1400958d9  add     rsp, 28h
0x1400958dd  pop     r14
0x1400958df  pop     r12
0x1400958e1  pop     rdi
0x1400958e2  pop     rsi
0x1400958e3  pop     rbp
0x1400958e4  pop     rbx
0x1400958e5  retn
```
