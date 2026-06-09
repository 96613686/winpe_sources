# CheckBootExecute

- ea: `0x140001390`
- end: `0x140001544`
- name: `CheckBootExecute`
- size: `436`
- prototype: `__int64 __fastcall(__int64, int, char *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400012f0`
- `0x140001338`
- `0x140001390`
- `0x140003711`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400013b7`
- `ntdll!RtlInitUnicodeString` at `0x14000152d`
- `ntdll!RtlInitUnicodeString` at `0x1400013b7`
- `ntdll!RtlInitUnicodeString` at `0x14000152d`
- `ntdll!RtlFreeHeap` at `0x140001521`
- `ntdll!RtlFreeHeap` at `0x140001521`

## pseudocode

```c
__int64 __fastcall CheckBootExecute(__int64 a1, int a2, char *a3, unsigned int a4)
{
  int appended; // ebx
  char *v8; // r15
  __int64 v9; // rsi
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  appended = AppendUnicodeString(&DestinationString, g_pwszArgv0);
  if ( appended >= 0 )
  {
    appended = AppendUnicodeString(&DestinationString, L" ");
    if ( appended >= 0 )
    {
      appended = AppendUnicodeString(&DestinationString, g_pwszArgv1);
      if ( appended >= 0 )
      {
        appended = AddToUnicodeString(&DestinationString, 0);
        if ( appended >= 0 )
        {
          if ( (unsigned int)(a2 - 1) <= 1 )
          {
            g_ulValueType = 1;
            g_fBootExecuteFound = 1;
            if ( memcmp_0(DestinationString.Buffer, a3, a4) )
            {
              appended = AppendUnicodeString(&g_ucsNewBootExecute, a3);
              if ( appended >= 0 )
                appended = AddToUnicodeString(&g_ucsNewBootExecute, 0);
            }
          }
          else if ( a2 == 7 )
          {
            g_fBootExecuteFound = 1;
            v8 = &a3[2 * ((unsigned __int64)a4 >> 1)];
            while ( a3 < v8 )
            {
              v9 = -1;
              do
                ++v9;
              while ( *(_WORD *)&a3[2 * v9] );
              if ( !(_DWORD)v9 )
                break;
              if ( (_DWORD)v9 != DestinationString.Length >> 1
                || memcmp_0(DestinationString.Buffer, a3, (unsigned int)v9) )
              {
                appended = AppendUnicodeString(&g_ucsNewBootExecute, a3);
                if ( appended < 0 )
                  goto LABEL_22;
                appended = AddToUnicodeString(&g_ucsNewBootExecute, 0);
                if ( appended < 0 )
                  goto LABEL_22;
              }
              a3 += 2 * (unsigned int)(v9 + 1);
            }
            appended = AddToUnicodeString(&g_ucsNewBootExecute, 0);
            if ( appended >= 0 )
              appended = 0;
          }
        }
      }
    }
  }
LABEL_22:
  if ( DestinationString.Buffer )
  {
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, DestinationString.Buffer);
    RtlInitUnicodeString(&DestinationString, 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140001390  push    rbp
0x140001392  push    rbx
0x140001393  push    rsi
0x140001394  push    rdi
0x140001395  push    r12
0x140001397  push    r14
0x140001399  push    r15
0x14000139b  mov     rbp, rsp
0x14000139e  sub     rsp, 30h
0x1400013a2  mov     esi, edx
0x1400013a4  mov     r14d, r9d
0x1400013a7  xorps   xmm0, xmm0
0x1400013aa  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400013ae  xor     edx, edx; SourceString
0x1400013b0  mov     rdi, r8
0x1400013b3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400013b7  call    cs:__imp_RtlInitUnicodeString
0x1400013bd  mov     rdx, cs:g_pwszArgv0
0x1400013c4  lea     rcx, [rbp+DestinationString]
0x1400013c8  call    AppendUnicodeString
0x1400013cd  xor     r12d, r12d
0x1400013d0  mov     ebx, eax
0x1400013d2  test    eax, eax
0x1400013d4  js      loc_140001508
0x1400013da  lea     rdx, asc_140004400; " "
0x1400013e1  lea     rcx, [rbp+DestinationString]
0x1400013e5  call    AppendUnicodeString
0x1400013ea  mov     ebx, eax
0x1400013ec  test    eax, eax
0x1400013ee  js      loc_140001508
0x1400013f4  mov     rdx, cs:g_pwszArgv1
0x1400013fb  lea     rcx, [rbp+DestinationString]
0x1400013ff  call    AppendUnicodeString
0x140001404  mov     ebx, eax
0x140001406  test    eax, eax
0x140001408  js      loc_140001508
0x14000140e  xor     edx, edx
0x140001410  lea     rcx, [rbp+DestinationString]
0x140001414  call    AddToUnicodeString
0x140001419  mov     ebx, eax
0x14000141b  test    eax, eax
0x14000141d  js      loc_140001508
0x140001423  lea     eax, [rsi-1]
0x140001426  mov     r8d, r14d; Size
0x140001429  cmp     eax, 1
0x14000142c  jbe     loc_1400014C3
0x140001432  cmp     esi, 7
0x140001435  jnz     loc_140001508
0x14000143b  shr     r8, 1
0x14000143e  lea     r14, g_ucsNewBootExecute
0x140001445  mov     cs:g_fBootExecuteFound, 1
0x14000144c  lea     r15, [rdi+r8*2]
0x140001450  jmp     short loc_1400014A9
0x140001452  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001456  inc     rsi
0x140001459  cmp     [rdi+rsi*2], r12w
0x14000145e  jnz     short loc_140001456
0x140001460  test    esi, esi
0x140001462  jz      short loc_1400014AE
0x140001464  movzx   eax, [rbp+DestinationString.Length]
0x140001468  shr     eax, 1
0x14000146a  cmp     esi, eax
0x14000146c  jnz     short loc_140001481
0x14000146e  mov     rcx, [rbp+DestinationString.Buffer]; Buf1
0x140001472  mov     rdx, rdi; Buf2
0x140001475  mov     r8d, esi; Size
0x140001478  call    memcmp_0
0x14000147d  test    eax, eax
0x14000147f  jz      short loc_1400014A2
0x140001481  mov     rdx, rdi
0x140001484  mov     rcx, r14
0x140001487  call    AppendUnicodeString
0x14000148c  mov     ebx, eax
0x14000148e  test    eax, eax
0x140001490  js      short loc_140001508
0x140001492  xor     edx, edx
0x140001494  mov     rcx, r14
0x140001497  call    AddToUnicodeString
0x14000149c  mov     ebx, eax
0x14000149e  test    eax, eax
0x1400014a0  js      short loc_140001508
0x1400014a2  lea     eax, [rsi+1]
0x1400014a5  lea     rdi, [rdi+rax*2]
0x1400014a9  cmp     rdi, r15
0x1400014ac  jb      short loc_140001452
0x1400014ae  xor     edx, edx
0x1400014b0  mov     rcx, r14
0x1400014b3  call    AddToUnicodeString
0x1400014b8  mov     ebx, eax
0x1400014ba  test    eax, eax
0x1400014bc  js      short loc_140001508
0x1400014be  mov     ebx, r12d
0x1400014c1  jmp     short loc_140001508
0x1400014c3  mov     rcx, [rbp+DestinationString.Buffer]; Buf1
0x1400014c7  mov     rdx, rdi; Buf2
0x1400014ca  mov     cs:g_ulValueType, 1
0x1400014d4  mov     cs:g_fBootExecuteFound, 1
0x1400014db  call    memcmp_0
0x1400014e0  test    eax, eax
0x1400014e2  jz      short loc_140001508
0x1400014e4  lea     r14, g_ucsNewBootExecute
0x1400014eb  mov     rdx, rdi
0x1400014ee  mov     rcx, r14
0x1400014f1  call    AppendUnicodeString
0x1400014f6  mov     ebx, eax
0x1400014f8  test    eax, eax
0x1400014fa  js      short loc_140001508
0x1400014fc  xor     edx, edx
0x1400014fe  mov     rcx, r14
0x140001501  call    AddToUnicodeString
0x140001506  mov     ebx, eax
0x140001508  cmp     [rbp+DestinationString.Buffer], r12
0x14000150c  jz      short loc_140001533
0x14000150e  mov     rcx, gs:60h
0x140001517  xor     edx, edx; Flags
0x140001519  mov     r8, [rbp+DestinationString.Buffer]; BaseAddress
0x14000151d  mov     rcx, [rcx+30h]; HeapHandle
0x140001521  call    cs:__imp_RtlFreeHeap
0x140001527  xor     edx, edx; SourceString
0x140001529  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000152d  call    cs:__imp_RtlInitUnicodeString
0x140001533  mov     eax, ebx
0x140001535  add     rsp, 30h
0x140001539  pop     r15
0x14000153b  pop     r14
0x14000153d  pop     r12
0x14000153f  pop     rdi
0x140001540  pop     rsi
0x140001541  pop     rbx
0x140001542  pop     rbp
0x140001543  retn
```
