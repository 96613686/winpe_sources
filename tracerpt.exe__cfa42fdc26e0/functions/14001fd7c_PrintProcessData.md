# PrintProcessData

- ea: `0x14001fd7c`
- end: `0x140020309`
- name: `PrintProcessData`
- size: `1421`
- prototype: `LPVOID *__fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140016ae0`

## callees

- `0x140016360`
- `0x1400164c4`
- `0x14001cc88`
- `0x14001ebc4`
- `0x14001fd7c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14001fedc`
- `msvcrt!_wcsicmp` at `0x14001fedc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400202af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400202af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001fef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400202a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001fef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400202a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ff0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ff0a`

## string_xrefs

- `0x1400201b4`: `	<Item>\n		<Data name='serviceName'>%s</Data>\n		<Data name='launchedThreads'>%d</Data>\n		<Data name='usedThreads'>%d</Data>\n		<Data name='kernelCpuPer'>%.4f</Data>\n		<Data name='userCpuPer'>%.4f</Data>\n		<Data name='cpu'>%.4f</Data>\n	</Item>\n`
- `0x14001fe52`: `	<Header>\n		<Data span='3' />\n		<Data name='threads' span='2' class='span'/>\n		<Data span='3'/>\n	</Header>\n`
- `0x14001fe61`: `	<Header>\n		<Sort field='cpu' type='number' order='descending'/>\n		<Sort field='image' type='text' order='ascending'/>\n		<Threshold type='top' field='count' value='3'/>\n		<Threshold type='octave' field='cpu'/>\n		<Data name='image' class='string'/>\n		<Data name='pid' class='string'/>\n		<Data name='launchedThreads' summary='total' class='number'/>\n		<Data name='usedThreads' summary='total' class='number'/>\n		<Data name='kernelCpuPer' class='number' format='#,##0.0'/>\n		<Data na`
- `0x14001fe70`: `		<Header>\n			<Sort field='cpu' type='number' order='descending'/>\n			<Sort field='process' type='text' order='ascending'/>\n			<Data name='serviceName' class='string'/>\n		<Data name='launchedThreads' class='number'/>\n		<Data name='usedThreads' class='number'/>\n			<Data name='kernelCpuPer' class='number' format='#,##0.0'/>\n			<Data name='userCpuPer' class='number' format='#,##0.0'/>\n			<Data name='cpu' class='number' format='#,##0.0'/>\n		</Header>\n`
- `0x140020157`: `		<Data name='pid'>%d</Data>\n		<Data name='launchedThreads'>%d</Data>\n		<Data name='usedThreads'>%d</Data>\n		<Data name='kernelCpuPer'>%.4f</Data>\n		<Data name='userCpuPer'>%.4f</Data>\n		<Data name='cpu'>%.4f</Data>\n		<Data name='groupCpu' visible='false'>%.4f</Data>\n`

## pseudocode

```c
LPVOID *__fastcall PrintProcessData(struct _iobuf *a1)
{
  struct _iobuf *v1; // r14
  LPVOID *result; // rax
  int v3; // edi
  int v4; // ebx
  double v5; // xmm11_8
  struct _PROCESS_RECORD *v6; // rsi
  double v7; // xmm7_8
  double v8; // xmm13_8
  double *v9; // rbx
  const wchar_t *v10; // rdi
  LPVOID *v11; // r15
  __int64 v12; // rax
  bool v13; // zf
  HANDLE ProcessHeap; // rax
  double *v15; // rax
  _QWORD *v16; // rax
  char *v17; // r15
  char *v18; // rdi
  int v19; // r12d
  int v20; // r13d
  int v21; // r14d
  unsigned int v22; // esi
  double v23; // xmm6_8
  const wchar_t *v24; // r8
  double v25; // xmm8_8
  double v26; // xmm1_8
  __int64 *v27; // rbx
  double v28; // xmm7_8
  LPVOID *v29; // rdi
  LPVOID v30; // rax
  LPVOID *v31; // rcx
  LPVOID *v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+58h] [rbp-B0h]
  struct _PROCESS_RECORD *v36; // [rsp+60h] [rbp-A8h]
  LPVOID lpMem; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID *p_lpMem; // [rsp+70h] [rbp-98h]
  struct _LIST_ENTRY v39[9]; // [rsp+78h] [rbp-90h] BYREF
  int v41; // [rsp+160h] [rbp+58h]
  unsigned int v42; // [rsp+168h] [rbp+60h]
  int v43; // [rsp+170h] [rbp+68h]

  v1 = a1;
  p_lpMem = &lpMem;
  result = &lpMem;
  lpMem = &lpMem;
  if ( &qword_140082130 == (struct _PROCESS_RECORD **)qword_140082130 )
    return result;
  v3 = 0;
  v35 = 0;
  v4 = 1;
  if ( dword_14008210C )
    v4 = dword_14008210C;
  v43 = v4;
  v5 = (double)(SystemTimeAsFileTime.dwLowDateTime - CurrentSystem.dwLowDateTime) / 10000000.0;
  TracerptFPutws((wchar_t *)L"<Table name='imageStats' level='1' key='100' topic='process'>\r\n", a1);
  TracerptFPutws(
    (wchar_t *)L"<Summary key='1' find='total' field='cpu' exclude='pid' value='0' topic='process'>\r\n"
                "  <Data name='totalCpu' format='#,##0'/>\r\n"
                "</Summary>\r\n"
                "<Summary key='1' find='top' field='groupCpu' exclude='pid' value='0' topic='process'>\r\n"
                "  <Data name='image' label='topProcessGroup'/>\r\n"
                "  <Data name='groupCpu' format='#,##0'/>\r\n"
                "</Summary>\r\n",
    v1);
  TracerptFPutws(
    (wchar_t *)L"\t<Header>\r\n"
                "\t\t<Data span='3' />\r\n"
                "\t\t<Data name='threads' span='2' class='span'/>\r\n"
                "\t\t<Data span='3'/>\r\n"
                "\t</Header>\r\n",
    v1);
  TracerptFPutws(
    (wchar_t *)L"\t<Header>\r\n"
                "\t\t<Sort field='cpu' type='number' order='descending'/>\r\n"
                "\t\t<Sort field='image' type='text' order='ascending'/>\r\n"
                "\t\t<Threshold type='top' field='count' value='3'/>\r\n"
                "\t\t<Threshold type='octave' field='cpu'/>\r\n"
                "\t\t<Data name='image' class='string'/>\r\n"
                "\t\t<Data name='pid' class='string'/>\r\n"
                "\t\t<Data name='launchedThreads' summary='total' class='number'/>\r\n"
                "\t\t<Data name='usedThreads' summary='total' class='number'/>\r\n"
                "\t\t<Data name='kernelCpuPer' class='number' format='#,##0.0'/>\r\n"
                "\t\t<Data name='userCpuPer' class='number' format='#,##0.0'/>\r\n"
                "\t\t<Data name='cpu' summary='total' class='number' format='#,##0.0'/>\r\n"
                "\t\t<Data name='groupCpu' class='number' format='#,##0.0' visible='false'/>\r\n",
    v1);
  TracerptFPutws(
    (wchar_t *)L"\t\t<Header>\r\n"
                "\t\t\t<Sort field='cpu' type='number' order='descending'/>\r\n"
                "\t\t\t<Sort field='process' type='text' order='ascending'/>\r\n"
                "\t\t\t<Data name='serviceName' class='string'/>\r\n"
                "\t\t<Data name='launchedThreads' class='number'/>\r\n"
                "\t\t<Data name='usedThreads' class='number'/>\r\n"
                "\t\t\t<Data name='kernelCpuPer' class='number' format='#,##0.0'/>\r\n"
                "\t\t\t<Data name='userCpuPer' class='number' format='#,##0.0'/>\r\n"
                "\t\t\t<Data name='cpu' class='number' format='#,##0.0'/>\r\n"
                "\t\t</Header>\r\n",
    v1);
  TracerptFPutws((wchar_t *)L"\t</Header>\r\n", v1);
  while ( 1 )
  {
    v6 = qword_140082130;
    v7 = 0.0;
    v8 = 0.0;
    while ( 1 )
    {
      v36 = v6;
      if ( v6 == (struct _PROCESS_RECORD *)&qword_140082130 )
        break;
      if ( !v3 )
        goto LABEL_7;
      v9 = (double *)lpMem;
      v10 = (const wchar_t *)*((_QWORD *)v6 + 13);
      if ( &lpMem != lpMem )
      {
        while ( 1 )
        {
          v11 = *(LPVOID **)v9;
          v12 = *((_QWORD *)v9 + 2);
          if ( !v10 )
            break;
          if ( v12 )
          {
            v13 = _wcsicmp(*((const wchar_t **)v9 + 2), v10) == 0;
            goto LABEL_13;
          }
LABEL_14:
          v9 = (double *)v11;
          if ( &lpMem == v11 )
            goto LABEL_15;
        }
        v13 = v12 == 0;
LABEL_13:
        if ( v13 )
          goto LABEL_18;
        goto LABEL_14;
      }
LABEL_15:
      ProcessHeap = GetProcessHeap();
      v15 = (double *)HeapAlloc(ProcessHeap, 8u, 0x20u);
      v9 = v15;
      if ( !v15 )
      {
LABEL_7:
        v9 = 0;
        goto LABEL_18;
      }
      *((_QWORD *)v15 + 2) = v10;
      v15[3] = 0.0;
      v16 = lpMem;
      if ( *((LPVOID **)lpMem + 1) != &lpMem )
LABEL_61:
        __fastfail(3u);
      *(_QWORD *)v9 = lpMem;
      *((_QWORD *)v9 + 1) = &lpMem;
      v16[1] = v9;
      lpMem = v9;
LABEL_18:
      v17 = (char *)v6 + 16;
      v41 = 0;
      v18 = (char *)*((_QWORD *)v6 + 2);
      v19 = 0;
      v20 = 0;
      v42 = 0;
      if ( v18 != (char *)v6 + 16 )
      {
        v21 = 0;
        v22 = 0;
        do
        {
          v39[0] = 0;
          if ( *((_DWORD *)v18 + 30)
            || *((_DWORD *)v18 + 31)
            || *((_DWORD *)v18 + 47) > *((_DWORD *)v18 + 46)
            || *((_DWORD *)v18 + 49) > *((_DWORD *)v18 + 48)
            || *((_DWORD *)v18 + 32)
            || *((_DWORD *)v18 + 33)
            || *((_DWORD *)v18 + 36) )
          {
            ++v21;
          }
          ++v22;
          v19 += dword_1400820F8 * (*((_DWORD *)v18 + 49) - *((_DWORD *)v18 + 48));
          v20 += dword_1400820F8 * (*((_DWORD *)v18 + 47) - *((_DWORD *)v18 + 46));
          v39[0].Blink = v39;
          v39[0].Flink = v39;
          CollapseTree(v18 + 32, v39, 1);
          DeleteTransList(v39, 0);
          v18 = *(char **)v18;
        }
        while ( v18 != v17 );
        v42 = v22;
        v6 = v36;
        v41 = v21;
        v1 = a1;
      }
      v23 = ((double)(v19 + v20) + 0.0) / v5 / 1000.0 * 100.0;
      if ( *((_DWORD *)v6 + 30) )
        v7 = v7 + v23;
      if ( v9 )
        v9[3] = v23 + v9[3];
      v3 = v35;
      if ( v35 )
      {
        TracerptFWPrintf(v1, (wchar_t *)L"\t<Item>\r\n");
        v24 = L"Idle";
        if ( *((_QWORD *)v6 + 13) )
          v24 = (const wchar_t *)*((_QWORD *)v6 + 13);
        TracerptFWPrintf(v1, (wchar_t *)L"\t\t<Data name='image'>%s", v24);
        if ( *((_QWORD *)v6 + 14) )
          TracerptFWPrintf(v1, (wchar_t *)L" (%s)");
        TracerptFWPrintf(v1, (wchar_t *)L"</Data>\r\n");
        v25 = (double)v43;
        if ( v9 )
          v26 = v9[3] / v25;
        else
          v26 = 0.0;
        LODWORD(v34) = v41;
        TracerptFWPrintf(
          v1,
          (wchar_t *)L"\t\t<Data name='pid'>%d</Data>\r\n"
                      "\t\t<Data name='launchedThreads'>%d</Data>\r\n"
                      "\t\t<Data name='usedThreads'>%d</Data>\r\n"
                      "\t\t<Data name='kernelCpuPer'>%.4f</Data>\r\n"
                      "\t\t<Data name='userCpuPer'>%.4f</Data>\r\n"
                      "\t\t<Data name='cpu'>%.4f</Data>\r\n"
                      "\t\t<Data name='groupCpu' visible='false'>%.4f</Data>\r\n",
          *((unsigned int *)v6 + 30),
          v42,
          v34,
          ((double)v20 + 0.0) / v5 / 1000.0 * 100.0 / v25,
          ((double)v19 + 0.0) / v5 / 1000.0 * 100.0 / v25,
          v23 / v25,
          v26);
        v27 = (__int64 *)*((_QWORD *)v6 + 4);
        if ( v27 != (__int64 *)((char *)v6 + 32) && *((_DWORD *)v6 + 30) )
        {
          do
          {
            LODWORD(v34) = *((_DWORD *)v27 + 27);
            TracerptFWPrintf(
              v1,
              (wchar_t *)L"\t<Item>\r\n"
                          "\t\t<Data name='serviceName'>%s</Data>\r\n"
                          "\t\t<Data name='launchedThreads'>%d</Data>\r\n"
                          "\t\t<Data name='usedThreads'>%d</Data>\r\n"
                          "\t\t<Data name='kernelCpuPer'>%.4f</Data>\r\n"
                          "\t\t<Data name='userCpuPer'>%.4f</Data>\r\n"
                          "\t\t<Data name='cpu'>%.4f</Data>\r\n"
                          "\t</Item>\r\n",
              v27[5],
              *((unsigned int *)v27 + 26),
              v34,
              v27[11],
              v27[12],
              v27[10]);
            v27 = (__int64 *)*v27;
          }
          while ( v27 != (__int64 *)((char *)v6 + 32) );
        }
        TracerptFWPrintf(v1, (wchar_t *)L"\t</Item>\r\n");
        v3 = v35;
        v4 = v43;
      }
      else
      {
        v4 = v43;
        v25 = (double)v43;
      }
      if ( !*((_DWORD *)v6 + 30) )
        v8 = v8 + v23 / v25;
      v6 = *(struct _PROCESS_RECORD **)v6;
    }
    if ( v3 )
      break;
    v28 = v7 / (double)v4 + v8;
    if ( v28 > 100.0 )
      v5 = v5 * (v28 / 100.0);
    v3 = 1;
    v35 = 1;
  }
  TracerptFPutws((wchar_t *)L"</Table>\r\n", v1);
  v29 = (LPVOID *)lpMem;
  while ( 1 )
  {
    result = &lpMem;
    if ( &lpMem == v29 )
      return result;
    v30 = *v29;
    if ( *((LPVOID **)*v29 + 1) != v29 )
      goto LABEL_61;
    v31 = (LPVOID *)v29[1];
    if ( *v31 != v29 )
      goto LABEL_61;
    *v31 = v30;
    v32 = v29;
    v29 = (LPVOID *)v30;
    *((_QWORD *)v30 + 1) = v31;
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v32);
  }
}

```

## disassembly

```asm
0x14001fd7c  mov     rax, rsp
0x14001fd7f  mov     [rax+8], rcx
0x14001fd83  push    rbp
0x14001fd84  push    rbx
0x14001fd85  push    rsi
0x14001fd86  push    rdi
0x14001fd87  push    r12
0x14001fd89  push    r13
0x14001fd8b  push    r14
0x14001fd8d  push    r15
0x14001fd8f  lea     rbp, [rax-48h]
0x14001fd93  sub     rsp, 108h
0x14001fd9a  movaps  xmmword ptr [rax-58h], xmm6
0x14001fd9e  lea     r15, qword_140082130
0x14001fda5  cmp     r15, cs:qword_140082130
0x14001fdac  mov     r14, rcx
0x14001fdaf  movaps  xmmword ptr [rax-68h], xmm7
0x14001fdb3  movaps  xmmword ptr [rax-78h], xmm8
0x14001fdb8  movaps  xmmword ptr [rax-88h], xmm9
0x14001fdc0  movaps  xmmword ptr [rax-98h], xmm10
0x14001fdc8  movaps  xmmword ptr [rax-0A8h], xmm11
0x14001fdd0  movaps  xmmword ptr [rax-0B8h], xmm13
0x14001fdd8  movaps  xmmword ptr [rax-0C8h], xmm14
0x14001fde0  lea     rax, [rsp+140h+lpMem]
0x14001fde5  mov     [rsp+140h+var_D8.Flink], rax
0x14001fdea  lea     rax, [rsp+140h+lpMem]
0x14001fdef  mov     [rsp+140h+lpMem], rax
0x14001fdf4  jz      loc_1400202BF
0x14001fdfa  mov     eax, cs:dword_14008210C
0x14001fe00  xor     edi, edi
0x14001fe02  test    eax, eax
0x14001fe04  mov     dword ptr [rsp+140h+var_F0], edi
0x14001fe08  xorps   xmm11, xmm11
0x14001fe0c  mov     rdx, rcx; struct _iobuf *
0x14001fe0f  lea     rcx, aTableNameImage; "<Table name='imageStats' level='1' key="...
0x14001fe16  lea     ebx, [rdi+1]
0x14001fe19  cmovnz  ebx, eax
0x14001fe1c  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14001fe23  sub     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x14001fe2a  mov     [rbp+40h+arg_18], ebx
0x14001fe2d  cvtsi2sd xmm11, rax
0x14001fe32  divsd   xmm11, cs:__real@416312d000000000
0x14001fe3b  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe40  mov     rdx, r14; struct _iobuf *
0x14001fe43  lea     rcx, aSummaryKey1Fin; "<Summary key='1' find='total' field='cp"...
0x14001fe4a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe4f  mov     rdx, r14; struct _iobuf *
0x14001fe52  lea     rcx, aHeaderDataSpan; "\t<Header>\r\n\t\t<Data span='3' />\r\n"...
0x14001fe59  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe5e  mov     rdx, r14; struct _iobuf *
0x14001fe61  lea     rcx, aHeaderSortFiel_3; "\t<Header>\r\n\t\t<Sort field='cpu' typ"...
0x14001fe68  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe6d  mov     rdx, r14; struct _iobuf *
0x14001fe70  lea     rcx, aHeaderSortFiel; "\t\t<Header>\r\n\t\t\t<Sort field='cpu'"...
0x14001fe77  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe7c  mov     rdx, r14; struct _iobuf *
0x14001fe7f  lea     rcx, aHeader_2; "\t</Header>\r\n"
0x14001fe86  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001fe8b  movsd   xmm14, cs:__real@4059000000000000
0x14001fe94  mov     rsi, cs:qword_140082130
0x14001fe9b  xorps   xmm7, xmm7
0x14001fe9e  xorps   xmm13, xmm13
0x14001fea2  jmp     loc_140020228
0x14001fea7  test    edi, edi
0x14001fea9  jnz     short loc_14001FEB2
0x14001feab  xor     ebx, ebx
0x14001fead  jmp     loc_14001FF4D
0x14001feb2  mov     rbx, [rsp+140h+lpMem]
0x14001feb7  lea     rax, [rsp+140h+lpMem]
0x14001febc  mov     rdi, [rsi+68h]
0x14001fec0  cmp     rax, rbx
0x14001fec3  jz      short loc_14001FEF8
0x14001fec5  mov     r15, [rbx]
0x14001fec8  mov     rax, [rbx+10h]
0x14001fecc  test    rdi, rdi
0x14001fecf  jz      short loc_14001FEE6
0x14001fed1  test    rax, rax
0x14001fed4  jz      short loc_14001FEEB
0x14001fed6  mov     rdx, rdi; String2
0x14001fed9  mov     rcx, rax; String1
0x14001fedc  call    cs:__imp__wcsicmp
0x14001fee2  test    eax, eax
0x14001fee4  jmp     short loc_14001FEE9
0x14001fee6  test    rax, rax
0x14001fee9  jz      short loc_14001FF4D
0x14001feeb  lea     rax, [rsp+140h+lpMem]
0x14001fef0  mov     rbx, r15
0x14001fef3  cmp     rax, r15
0x14001fef6  jnz     short loc_14001FEC5
0x14001fef8  call    cs:__imp_GetProcessHeap
0x14001fefe  mov     edx, 8; dwFlags
0x14001ff03  mov     rcx, rax; hHeap
0x14001ff06  lea     r8d, [rdx+18h]; dwBytes
0x14001ff0a  call    cs:__imp_HeapAlloc
0x14001ff10  mov     rbx, rax
0x14001ff13  test    rax, rax
0x14001ff16  jz      short loc_14001FEAB
0x14001ff18  mov     [rax+10h], rdi
0x14001ff1c  lea     rcx, [rsp+140h+lpMem]
0x14001ff21  mov     qword ptr [rax+18h], 0
0x14001ff29  mov     rax, [rsp+140h+lpMem]
0x14001ff2e  cmp     [rax+8], rcx
0x14001ff32  jnz     loc_140020302
0x14001ff38  mov     [rbx], rax
0x14001ff3b  lea     rcx, [rsp+140h+lpMem]
0x14001ff40  mov     [rbx+8], rcx
0x14001ff44  mov     [rax+8], rbx
0x14001ff48  mov     [rsp+140h+lpMem], rbx
0x14001ff4d  lea     r15, [rsi+10h]
0x14001ff51  mov     [rbp+40h+arg_8], 0
0x14001ff58  mov     rdi, [r15]
0x14001ff5b  xor     r12d, r12d
0x14001ff5e  xor     r13d, r13d
0x14001ff61  mov     [rbp+40h+arg_10], 0
0x14001ff68  cmp     rdi, r15
0x14001ff6b  jz      loc_140020040
0x14001ff71  mov     r14d, r12d
0x14001ff74  mov     esi, r12d
0x14001ff77  xorps   xmm0, xmm0
0x14001ff7a  xor     ecx, ecx
0x14001ff7c  movups  xmmword ptr [rsp+140h+var_D8.Blink], xmm0
0x14001ff81  cmp     [rdi+78h], ecx
0x14001ff84  jnz     short loc_14001FFBF
0x14001ff86  cmp     [rdi+7Ch], ecx
0x14001ff89  jnz     short loc_14001FFBF
0x14001ff8b  mov     eax, [rdi+0B8h]
0x14001ff91  cmp     [rdi+0BCh], eax
0x14001ff97  ja      short loc_14001FFBF
0x14001ff99  mov     eax, [rdi+0C0h]
0x14001ff9f  cmp     [rdi+0C4h], eax
0x14001ffa5  ja      short loc_14001FFBF
0x14001ffa7  cmp     [rdi+80h], ecx
0x14001ffad  jnz     short loc_14001FFBF
0x14001ffaf  cmp     [rdi+84h], ecx
0x14001ffb5  jnz     short loc_14001FFBF
0x14001ffb7  cmp     [rdi+90h], ecx
0x14001ffbd  jz      short loc_14001FFC2
0x14001ffbf  inc     r14d
0x14001ffc2  mov     eax, [rdi+0C4h]
0x14001ffc8  lea     rcx, [rdi+20h]
0x14001ffcc  sub     eax, [rdi+0C0h]
0x14001ffd2  lea     rdx, [rsp+140h+var_D8.Blink]
0x14001ffd7  imul    eax, cs:dword_1400820F8
0x14001ffde  mov     r8d, 1
0x14001ffe4  inc     esi
0x14001ffe6  add     r12d, eax
0x14001ffe9  mov     eax, [rdi+0BCh]
0x14001ffef  sub     eax, [rdi+0B8h]
0x14001fff5  imul    eax, cs:dword_1400820F8
0x14001fffc  add     r13d, eax
0x14001ffff  lea     rax, [rsp+140h+var_D8.Blink]
0x140020004  mov     [rsp+140h+var_C8], rax
0x140020009  lea     rax, [rsp+140h+var_D8.Blink]
0x14002000e  mov     [rsp+140h+var_D8.Blink], rax
0x140020013  call    CollapseTree
0x140020018  xor     edx, edx; unsigned int
0x14002001a  lea     rcx, [rsp+140h+var_D8.Blink]; struct _LIST_ENTRY *
0x14002001f  call    ?DeleteTransList@@YAEPEAU_LIST_ENTRY@@K@Z; DeleteTransList(_LIST_ENTRY *,ulong)
0x140020024  mov     rdi, [rdi]
0x140020027  cmp     rdi, r15
0x14002002a  jnz     loc_14001FF77
0x140020030  mov     [rbp+40h+arg_10], esi
0x140020033  mov     rsi, [rsp+140h+var_E8]
0x140020038  mov     [rbp+40h+arg_8], r14d
0x14002003c  mov     r14, [rbp+40h+arg_0]
0x140020040  cmp     dword ptr [rsi+78h], 0
0x140020044  lea     ecx, [r12+r13]
0x140020048  xorps   xmm6, xmm6
0x14002004b  cvtsi2sd xmm6, rcx
0x140020050  addsd   xmm6, cs:__real@0000000000000000
0x140020058  divsd   xmm6, xmm11
0x14002005d  divsd   xmm6, cs:__real@408f400000000000
0x140020065  mulsd   xmm6, xmm14
0x14002006a  jz      short loc_140020070
0x14002006c  addsd   xmm7, xmm6
0x140020070  test    rbx, rbx
0x140020073  jz      short loc_140020082
0x140020075  movaps  xmm0, xmm6
0x140020078  addsd   xmm0, qword ptr [rbx+18h]
0x14002007d  movsd   qword ptr [rbx+18h], xmm0
0x140020082  mov     edi, dword ptr [rsp+140h+var_F0]
0x140020086  test    edi, edi
0x140020088  jz      loc_140020202
0x14002008e  xorps   xmm10, xmm10
0x140020092  mov     eax, r13d
0x140020095  xorps   xmm9, xmm9
0x140020099  lea     rdx, aItem_0; "\t<Item>\r\n"
0x1400200a0  mov     rcx, r14; struct _iobuf *
0x1400200a3  cvtsi2sd xmm10, rax
0x1400200a8  mov     eax, r12d
0x1400200ab  cvtsi2sd xmm9, rax
0x1400200b0  addsd   xmm10, cs:__real@0000000000000000
0x1400200b9  addsd   xmm9, cs:__real@0000000000000000
0x1400200c2  divsd   xmm10, xmm11
0x1400200c7  divsd   xmm9, xmm11
0x1400200cc  divsd   xmm10, cs:__real@408f400000000000
0x1400200d5  divsd   xmm9, cs:__real@408f400000000000
0x1400200de  mulsd   xmm10, xmm14
0x1400200e3  mulsd   xmm9, xmm14
0x1400200e8  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400200ed  cmp     qword ptr [rsi+68h], 0
0x1400200f2  lea     r8, aIdle; "Idle"
0x1400200f9  lea     rdx, aDataNameImageS; "\t\t<Data name='image'>%s"
0x140020100  mov     rcx, r14; struct _iobuf *
0x140020103  cmovnz  r8, [rsi+68h]
0x140020108  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14002010d  mov     r8, [rsi+70h]
0x140020111  test    r8, r8
0x140020114  jz      short loc_140020125
0x140020116  lea     rdx, aS; " (%s)"
0x14002011d  mov     rcx, r14; struct _iobuf *
0x140020120  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020125  lea     rdx, aData; "</Data>\r\n"
0x14002012c  mov     rcx, r14; struct _iobuf *
0x14002012f  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020134  mov     eax, [rbp+40h+arg_18]
0x140020137  xorps   xmm8, xmm8
0x14002013b  cvtsi2sd xmm8, rax
0x140020140  test    rbx, rbx
0x140020143  jnz     short loc_14002014A
0x140020145  xorps   xmm1, xmm1
0x140020148  jmp     short loc_140020154
0x14002014a  movsd   xmm1, qword ptr [rbx+18h]
0x14002014f  divsd   xmm1, xmm8
0x140020154  mov     eax, [rbp+40h+arg_8]
0x140020157  lea     rdx, aDataNamePidDDa_0; "\t\t<Data name='pid'>%d</Data>\r\n\t\t<"...
0x14002015e  mov     r9d, [rbp+40h+arg_10]
0x140020162  movaps  xmm0, xmm6
0x140020165  mov     r8d, [rsi+78h]
0x140020169  mov     rcx, r14; struct _iobuf *
0x14002016c  movsd   [rsp+140h+var_100], xmm1
0x140020172  divsd   xmm0, xmm8
0x140020177  divsd   xmm9, xmm8
0x14002017c  movsd   [rsp+140h+var_108], xmm0
0x140020182  divsd   xmm10, xmm8
0x140020187  movsd   [rsp+140h+var_110], xmm9
0x14002018e  movsd   qword ptr [rsp+140h+var_120+8], xmm10
0x140020195  mov     dword ptr [rsp+140h+var_120], eax
0x140020199  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14002019e  lea     rdi, [rsi+20h]
0x1400201a2  mov     rbx, [rdi]
0x1400201a5  cmp     rbx, rdi
0x1400201a8  jz      short loc_1400201EA
0x1400201aa  cmp     dword ptr [rsi+78h], 0
0x1400201ae  jz      short loc_1400201EA
0x1400201b0  movups  xmm1, xmmword ptr [rbx+58h]
0x1400201b4  lea     rdx, aItemDataNameSe_0; "\t<Item>\r\n\t\t<Data name='serviceName"...
0x1400201bb  mov     eax, [rbx+6Ch]
0x1400201be  movsd   xmm0, qword ptr [rbx+50h]
0x1400201c3  mov     rcx, r14; struct _iobuf *
0x1400201c6  mov     r9d, [rbx+68h]
0x1400201ca  mov     r8, [rbx+28h]
0x1400201ce  movsd   [rsp+140h+var_108], xmm0
0x1400201d4  movups  [rsp+140h+var_120+8], xmm1
0x1400201d9  mov     dword ptr [rsp+140h+var_120], eax
0x1400201dd  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400201e2  mov     rbx, [rbx]
0x1400201e5  cmp     rbx, rdi
0x1400201e8  jnz     short loc_1400201B0
0x1400201ea  lea     rdx, aItem_1; "\t</Item>\r\n"
0x1400201f1  mov     rcx, r14; struct _iobuf *
0x1400201f4  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400201f9  mov     edi, dword ptr [rsp+140h+var_F0]
0x1400201fd  mov     ebx, [rbp+40h+arg_18]
0x140020200  jmp     short loc_14002020E
0x140020202  mov     ebx, [rbp+40h+arg_18]
0x140020205  xorps   xmm8, xmm8
0x140020209  cvtsi2sd xmm8, rbx
0x14002020e  cmp     dword ptr [rsi+78h], 0
0x140020212  jnz     short loc_14002021E
0x140020214  divsd   xmm6, xmm8
0x140020219  addsd   xmm13, xmm6
0x14002021e  mov     rsi, [rsi]
0x140020221  lea     r15, qword_140082130
0x140020228  mov     [rsp+140h+var_E8], rsi
0x14002022d  cmp     rsi, r15
0x140020230  jnz     loc_14001FEA7
0x140020236  test    edi, edi
0x140020238  jnz     short loc_14002026C
0x14002023a  mov     eax, ebx
0x14002023c  xorps   xmm0, xmm0
0x14002023f  cvtsi2sd xmm0, rax
0x140020244  divsd   xmm7, xmm0
0x140020248  addsd   xmm7, xmm13
0x14002024d  comisd  xmm7, xmm14
0x140020252  jbe     short loc_14002025E
0x140020254  divsd   xmm7, xmm14
0x140020259  mulsd   xmm11, xmm7
0x14002025e  mov     edi, 1
0x140020263  mov     dword ptr [rsp+140h+var_F0], edi
0x140020267  jmp     loc_14001FE94
0x14002026c  mov     rdx, r14; struct _iobuf *
0x14002026f  lea     rcx, aTable_0; "</Table>\r\n"
0x140020276  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002027b  mov     rdi, [rsp+140h+lpMem]
0x140020280  jmp     short loc_1400202B5
0x140020282  mov     rax, [rdi]
0x140020285  cmp     [rax+8], rdi
0x140020289  jnz     short loc_140020302
0x14002028b  mov     rcx, [rdi+8]
  ... truncated ...
```
